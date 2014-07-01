---
layout: post
title:  "Creating a Content Slider"
date:   2014-06-30 
categories: css 
---

Exercise in creating a Content slider that offers content on separate blocks.

<head>
<meta charset="utf-8">
<meta content="stuff, to, help, search, engines, not" name="keywords">
<meta content="What this page is about." name="description">
<meta content="An Interesting Title Goes Here" name="title">
<title>Content Slider</title>
 
<style>
#wrapper {
    width: 2200px;
    position: relative;
    left: 0px;
    transition: left .5s ease-in-out;
}

.content {
    float: left; 
    height: 350px;
    white-space: normal;
    width: 550px;
} 

#contentContainer {
    width: 550px;
    height: 350px;
    border: 5px black solid;
    overflow: hidden;
}

#itemOne {
    background-color: #ADFF2F;
}

#itemTwo {
    background-color: #FF7F50;
}

#itemThree {
    background-color: #1E90FF;
}

#itemFour {
    background-color: #DC143C;
}

#navLinks {
    text-align: center;
    width: 550px;
}

#navLinks ul {
    margin: 0px;
    padding: 0px;
    display: inline-block;
    margin-top: 6px;
}

#navLinks ul li {
    font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
    float: left;
    width: 25px;
    height: 23px;
    text-align: center;
    margin: 10px;
    list-style: none;
    cursor: pointer;
    background-color: #CCCCCC;
    outline: #333 solid 3px;
    padding-top: 2px;
}

#navLinks ul li:hover {
    background-color: #FFFF00;
}

#navLinks ul li.active {
    background-color: #333333;
    color: #FFFFFF;
    outline-width: 7px;
}

#navLinks ul li.active:hover {
    background-color: #484848;
    color: #FFFFFF;
}
</style>


</head>
 
<body>

<div id="contentContainer">

    <div id="wrapper">

        <div id="itemOne" class="content">

Main text

        </div>

        <div id="itemTwo" class="content">

Second text section.
 
        </div>

        <div id="itemThree" class="content">

Third text section.
 
        </div>

        <div id="itemFour" class="content">
 
Fourth text section.

        </div>

    </div>

</div>
 
<div id="navLinks">
    <ul>
        <li class="itemLinks" data-pos="0px">1</li>
        <li class="itemLinks" data-pos="-550px">2</li>
        <li class="itemLinks" data-pos="-1100px">3</li>
        <li class="itemLinks" data-pos="-1650px">4</li>
    </ul>
</div>
 
<script>
var links = document.querySelectorAll(".itemLinks");
var wrapper = document.querySelector("#wrapper");
 
for (var i = 0; i < links.length; i++) {
    var link = links[i];
    link.addEventListener('click', setPosition, false);
}
 
addClass(links[0], "active");
 
function setPosition(e) {
    removeActiveLinks();
 
    var clickedLink = e.target;
    addClass(clickedLink, "active");
     
    var position = clickedLink.getAttribute("data-pos");
    wrapper.style.left = position;
}
 
function removeActiveLinks() {
    for (var i = 0; i < links.length; i++) {
        removeClass(links[i], "active");
    }
}
 
function addClass(element, classToAdd) {
    var currentClassValue = element.className;
      
    if (currentClassValue.indexOf(classToAdd) == -1) {
        if ((currentClassValue == null) || (currentClassValue === "")) {
            element.className = classToAdd;
        } else {
            element.className += " " + classToAdd;
        }
    }
}
 
function removeClass(element, classToRemove) {
    var currentClassValue = element.className;
      
    // removing a class value when there is more than one class value present
    // and the class you want to remove is not the first one
    if (currentClassValue.indexOf(" " + classToRemove) != -1) {
        element.className = element.className.replace(" " + classToRemove, "");
        return;
    }
      
    // removing the first class value when there is more than one class
    // value present
    if (currentClassValue.indexOf(classToRemove + " ") != -1) {
        element.className = element.className.replace(classToRemove + " ", "");
        return;
    }
      
    // removing the first class value when there is only one class value
    // present
    if (currentClassValue.indexOf(classToRemove) != -1) {
        element.className = element.className.replace(classToRemove, "");
        return;
    }
} 
</script>

</body>








### References: 
