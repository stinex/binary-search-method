# binary-search-method

let arr = new Array(100)
  .fill(1)
  .map((a, i) => i)
  .reverse()
  .map.call("_".repeat(100), (a, i) => i);

const search = 32;

let i = 1,
  start = 0,
  end = arr.length - 1;

const searchNumber = () => {
  let condidat = arr[Math.round((end + start) / 2)];

  if (condidat === search)
    return console.log(`We found the number ${search} in ${i} function calls`);

  i = ++i;

  if (condidat < search) {
    console.log(`${condidat} < ${search}`);
    start = ++condidat;
    searchNumber();
  }

  if (condidat > search) {
    console.log(`${condidat} > ${search}`);
    end = --condidat;
    searchNumber();
  }
};

searchNumber();
