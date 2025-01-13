let cities = ["City A", "City B", "City C", "City D"];
let populations = [];

function setup() {
  createCanvas(400, 400);
  // Create fake populations for the cities
  for (let i = 0; i < cities.length; i++) {
    let fakePopulation = random(100000, 10000000); // Random population between 100,000 and 10 million
    populations.push(fakePopulation);
  }
}

function draw() {
  background(220);

  // Map population to circle size
  for (let i = 0; i < cities.length; i++) {
    let size = map(populations[i], 100000, 10000000, 20, 100); // Map population to circle size range
    let x = map(i, 0, cities.length, 50, width - 50);
    let y = height / 2;

    fill(255, 0, 0);
    ellipse(x, y, size, size);
  }
}
