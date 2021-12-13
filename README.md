<!DOCTYPE html>
<html lang="en">
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!--codingmaker-->
    <title>Automcompletesearch</title>
    <!-- Google Font -->
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins&display=swap"
      rel="stylesheet"/>
    <!-- Stylesheet -->
    <style>
      
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}
body {
  height: 100vh;
  background: linear-gradient(135deg,  #1a1a1a
, #000);
}
form {
  width: 75vmin;
  height: 100%;
  position: absolute;
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  padding: 40px 0;
}
input[type="text"] {
  width: 100%;
  padding: 15px 10px;
  border: none;
  border-bottom: 1px solid #645979;
  outline: none;
  border-radius: 8px 8px 0 0;
  background-color: #fff;
  font-size: 20px;
}
ul {
  list-style: none;
}
.list {
  width: 100%;
  background-color: #ffffff;
  border-radius:  9px 9px 9px 9px;
}
.list-items {
  padding: 10px 5px;
}
.list-items:hover {
  background-color: #ccc;
}

    </style>
  </head>
  <body>
    <form autocomplete="off" >
      <div> <input type="text" id="input" placeholder="Type to search.."/>
      </div>
      <ul class="list"></ul>
    </form>
    <!--JavaScript-->
    <script >
      /* */
let names = [
   "CodingMak",
    "CodingMaker",
    "YouTube",
    "YouTube cod",
    "YouTube CodingMak",
    "YouTube CodingMaker",
    "YouTuber",
    "YouTube Channel",
    "Blogger",
    "Facebook",
    "Freelancer",
    "Facebook Page",
    "Developer",
    "Web Designer",
    "website Developer",
    "Login Form in HTML & CSS",
    "How to learn HTML & CSS",
    "How to learn JavaScript",
    "How to became Freelancer",
    "How to became Web Designer",
    "How to start Gaming Channel",
    "How to start YouTube Channel",
    "What does HTML stands for?",
    "What does CSS stands for?",
];
let sortedNames = names.sort();
let input = document.getElementById("input");
input.addEventListener("keyup", (e) => {
   removeElements();
  for (let i of sortedNames) {
    if (
      i.toLowerCase().startsWith(input.value.toLowerCase()) &&
      input.value != ""
    ) {
      let listItem = document.createElement("li");
      listItem.classList.add("list-items");
      listItem.style.cursor = "pointer";
      listItem.setAttribute("onclick", 
        "displayNames('" + i + "')");
      let word = "<b>" + i.substr
      (0, input.value.length) + "</b>";
      word += i.substr(input.value.length);
      listItem.innerHTML = word;
      document.querySelector
      (".list").appendChild(listItem);
    }
  }
});
function displayNames(value) {
  input.value = value;
  removeElements();
}
function removeElements() {
  let items = document.querySelectorAll(".list-items");
  items.forEach((item) => {
    item.remove();
  });
}

    </script>
  </body>
</html>
