# DOM-Manipulation
let quotes = [
  `I live my life a quarter mile at a time`,
  `I said a ten-second car, not a ten-minute car`,
  `You can have any brew you want... as long as it's a Corona.`,
  `You almost had me? You never had me - you never had your car!`,
  `I don't have friends. I have family.`,
  `It don't matter if you win by an inch or a mile. Winning's winning.`
];



//part1
let mainTitleEl = document.getElementById('main-title'); //part 1
mainTitleEl.textContent = 'Welcome to the DOM';

//part 2
let bodyEl = document.querySelector('body'); //part 2
bodyEl.style.backgroundColor = 'teal';

//part 3
let favThingsEl = document.getElementById('favorite-things'); //part 3
favThingsEl.lastElementChild.remove();

//part 4
let specialTitleEl = document.querySelectorAll('.special-title');
console.log(specialTitleEl);
// specialTitleEl.style.fontSize = '2rem'; 
specialTitleEl.forEach(function(elem) {
elem.style.fontSize = '2rem';
});


//part 5
let pastRacesEl = document.getElementById('past-races')
console.log(pastRacesEl);

let pastRacesListArray = document.querySelectorAll('#past-races > li')
console.log(pastRacesListArray);
pastRacesListArray.forEach(function(li) {
  if(li.textContent === 'Chicago') {
  li.remove();
  return;
  }
});


//part 6
let newLiEl = document.createElement('li')
newLiEl.textContent = "Miami";

let pastRacesUlEl = document.getElementById('past-races');
pastRacesUlEl.append(newLiEl);


// Part 7
let mainEl = document.querySelector('.main');
console.log(mainEl)

let newBlogDiv = document.createElement('div');
newBlogDiv.classList.add('blog-post', 'purple');

let newBlogH1 = document.createElement('h1');
newBlogH1.textContent = newLiEl.textContent;

let newBlogP = document.createElement('p');
newBlogP.textContent = "I RACED ACROSS THE BEACHES!";

newBlogDiv.append(newBlogH1, newBlogP);
mainEl.append(newBlogDiv);


//part 8

const randomQuote = function() {
  document.querySelector('#quote-of-the-day').innerText = `"${quotes[Math.floor(Math.random() * quotes.length)]}"`;
};
let quoteTitleEl = document.getElementById('quote-title');
quoteTitleEl.addEventListener('click', function() {
randomQuote();
} )

//part 9

let allBlogPosts = document.getElementsByClassName('.blog-post');
console.log(allBlogPosts);
allBlogPosts.forEach(function() {
 blogpost.addEventListner('mouseout', function() {
  blogpost.classList.toggle ('purple');
  
 });
 blogpost.addEventListener('mouseenter', function() {
  blogpost.classList.toggle('red');

 });
});
