## [rsschool-cv](rsschool-cv)
***
## Sergei Drozdovski
***
### Junior Frontend Developer
****
### Contact information:

**Phone:** +7 988 5254601<br />
**E-mail:** sergiodrovski@gmail.com<br />
**Telegram:** @SergiDr<br />

### About Me:
Graduated from the Technical University with a degree in automated control systems.
After working for several years in the gas industry, he switched to web development for a vacancy HTML coder.
As a child, I liked to assemble and disassemble the bike, maybe that's what led me into development :))

****
### Skills:

* HTML5, CSS3
* JavaScript
* PHP
* Docker and docker-compose
* Server:
    + Apache (LAMP)
    + Nginx (LNMP)
* DB:
    + MySql
* Frameworks:
    + bundle React, Redux, React Router (Basics)
    + Php Slim (Basics)

### Code Example
***
Comment Tree
```
const comments = {
  1: {"id":1,"name":"Sergei","text":"comment text 1","date":"2022-09-13 13:10:52"},
  2: {"id":2,"name":"Djora","text":"comment text 2","date":"2022-09-13 19:13:52"},
  3: {"id":3,"name":"Jakarta","text":"comment text 3","date":"2022-09-13 13:45:21","parent_id":1},
  4: {"id":4,"name":"Test","text":"comment text 4","date":"2022-09-13 15:14:06","parent_id":3},
  5: {"id":5,"name":"Rustem","text":"comment text 8","date":"2022-09-13 15:16:06","parent_id":3},
  6: {"id":6,"name":"Faruk","text":"comment text 5","date":"2022-09-13 12:17:51"},
  7: {"id":7,"name":"Fredi","text":"comment text 6","date":"2022-09-13 15:13:06"}
}

function renderComments(commentsObj) {
  // sort data
  const commentsArr = Object.values(commentsObj)
  commentsArr.sort((a, b) => Date.parse(a.date) - Date.parse(b.date))

  const commentsBlock = document.createElement('div')
  commentsBlock.className = 'comments'

  commentsArr.forEach(elem => {
    syncComment(commentsBlock, commentsObj, elem)
  })
  return commentsBlock
}

function syncComment(commentsBlock, comments, elem) {
  if (commentsBlock.querySelector(`#comment${elem.id}`) !== null ) {
    return false
  }
  if (elem.parent_id) {
    syncComment(commentsBlock, comments, comments[elem.parent_id])
    let parent = commentsBlock.querySelector(`#comment${elem.parent_id}`);
    let commentChild = createEl(elem);
    parent.append(commentChild);
    return false
  }
  let commentEl = createEl(elem);
  commentsBlock.append(commentEl);
}


function createEl(comment) {
  const commentEl = document.createElement('div');
  commentEl.setAttribute('id', `comment${comment.id}`);
  commentEl.innerHTML = `
    <div>${comment.id}</div>
    <div>${comment.name}</div>
    <div>${comment.text}</div>
    <div>${comment.date}</div>
  `;
  return commentEl;
}
const res = renderComments(comments);
console.log(res)
``` 

### Education
****
* **University:** Kuban State Technological University
* **Courses:**
    + [HTML Academy](https://htmlacademy.ru/)
    + [Hexlet.io](https://ru.hexlet.io/)
    + [learn.javascript.ru](https://learn.javascript.ru/)

### English
****
* English - Basic
* Russian - Native