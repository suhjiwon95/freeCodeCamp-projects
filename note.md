# HTML - FORM

# to change inline to block element
    Use 'display: block': this separates inline elements

# submit button:
    <input type='submit' value='Submit' required />
    - required attribute makes form more interactive.
        if you try to submit the form without filling the text box, 
            an error message will show

# nesting <input/> in <label> allows not to specify 'for' and 'id'
    <label> Enter your name: <input type='text' /></label>

# <fieldset> separates similar form elements by drawing a box
    <fieldset>
        <label> input element 1: <input type='text' /></label>
    </fieldset>

    <fieldset>
        <label> input element 2: <input type='text' /></label>
    </fieldset>

    <fieldset>
        <label> input element 3: <input type='text' /></label>
    </fieldset>

# <legend> sets caption for <fieldset>
<form action="/action_page.php">
  <fieldset>
    <legend>Personalia:</legend>
    <label for="fname">First name:</label>
    <input type="text" id="fname" name="fname"><br><br>
    <label for="lname">Last name:</label>
    <input type="text" id="lname" name="lname"><br><br>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email"><br><br>
    <label for="birthday">Birthday:</label>
    <input type="date" id="birthday" name="birthday"><br><br>
    <input type="submit" value="Submit">
  </fieldset>
</form>

# 'minlength' attribute to type='password' will prevent less than min length of password submitted
    <input type='password' minlength='8' required />

# 'pattern' attribute to set regex that should match when password was typed
    <input type='password' pattern='[a-z0-5]{8,}' required/>
    - match 8 or more letters a - z or 0 to 5

# type="radio" and type="checkbox"
    <input type='checkbox' required />
    - for terms & condition checkbox. 
    - required; requires users to select the box
    
    <input type='radio' name='form1' />
    - circle selection button 
    - name: to specify the name of form element. Different name references different data sent.
        - name also allows to select one of the radio buttons

# type='file' to upload a profile picture
    <label> <input type='file' /> Upload a profile picture: </label>

# min and max attribute in <input>
    <label> <input type='number' min='13' max='120' /> Input your age (years): </label>
    - sets the number range of 13 to 120
    - submitting a number that is out of this range will show an error message.

# adding a dropdown menu with <select> and <option> elements.
    <select>: container for <option>
    <option>: works like <label> for each dropdown menu
        - within <option>, give a 'value' attribute that gives a value to each option
            when it is sent to the server.

    <label>How did you hear about us?
        <select name="referrer">
            <option value="">(Select one)</option>
            <option value="1">option1</option>
            <option value="2">option2</option>
            <option value="3">option3</option>
        </select>
    </label> 

# <textarea> gives a multiple line text field
    - 'rows' and 'cols' initial size of text field.
    - 'placeholder' displays texts until user starts typing
    <label> Tell us about yourself
        <textarea name="bio" rows="3" cols="20" placeholder="Enter your text here"></textarea>
    </label>

# giving 'name' attribute to submmitable elements to identify elements when form submission.
    - except for the type='radio'

# form submission to a specific webpage
    <main>
        <form method='post' action='https://freecodecamp.org/practice-project/accessibility-quiz'>
            <section></section>
            <section></section>
            <section></section>
        </form>
    </main>

# centering text item
    margin: 1em auto;
    text-align: center;


# centering a block element
    margin: 0 auto;

# max-width and min-width to set max and min width

# difference between 'width: 100vw' and 'width:100%'
    width: 100vw = the element will take 100 of width of the available screen,including the document margin
        - setting elements to vw will ensure that the proportion will be the same on any screen sizes. 
        - however, if your element size is bigger than 100vw, the horizontal scrollbar will show.
            Then use 100% instead.

    width: 100% = elements will fit all the space avaliable.
        - if a child element with width:100% is within a parent element, it will take up the 100% of total width of parent element.

# selecting all elements but the last element
    use :not(:last-of-type) pseudo-class

    fieldset:not(:last-of-type) {
        border-bottom: 3px solid #fffff;
    }

    - :not() can be ussed in any element
        span:not(sr-only) {
            font-weight: bold;
        }


# unset the width rule
    width: unset;

# aligning elements horizontally
    vertical-align: middle;
    (element 위 아래의 비율이 같게함으로써 vertical.)

# attribute selector
    selects an specific element based on a given attribute value.
    input[type='submit']{
        display: block;
    }
    input[name='password']{

    }

# overflow: hidden to set box size to original size
    - also prevents the text or contents overlaping each other. 

# clear: right
    - will clear the float property
    - push down the divider and any contents below the float: right element.

# div:not(#example) {
    color: red;
}
    - this will select all div that is not #example, and then apply color: red to all div except #example.

# <meta> in <head>
 <html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="freeCodeCamp Accessibility Quiz practice project" />
    <title>Accessibility Quiz</title>
    <link rel="stylesheet" href="styles.css" />
  </head>

# logo css
#logo {
  width: max(100px, 18vw);
	background-color: #0a0a23;
	aspect-ratio: 35/4;
	padding: 0.4rem;
}

# min(value1, value2)
    - set minimum width size to whichever value is the smallest 
    - when screen size changes, size of width changes accordingly. 
    - https://web.dev/min-max-clamp/
    header{
        width: min(50vw, 400px);
    }

# use flexbox and space contents evenly
	display: flex;
	justify-content: space-evenly;

# use role attribute to increase accecibility
    - to tag or navigate region where the form was submitted
    * role attribute requires aria attribute.
<form method="post" action="https://freecodecamp.org/practice-project/accessibility-quiz">
        <section role='region' aria-labelledby='student-info'>
            <h2>student-info</h2>
        </section>
        <section role='region' aria-labelledby='css-questions'>
            <h2>css questions</h2>
        </section>
      </form>

# setting multiple font-family, in case the web doesn't support font
    h1 {
        font-family: "Verdana", "Tahoma", sans-serif;
    }
# in <label>, for attribute connects to the corresponding <input> by sharing a same id name
    <label for='student-info'></label>
    <input id='student-info' />

# common pattern to make invisible text for screen reader
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}

# ::before , ::after 
    - pseudo-element.
    - you can add anything before or after the selected element

    HTML:
    <p>1</p>
    <p>2</p>
    <p>3</p>

    CSS:
    p::before {
        content: "Question ";
    }

    Output:
    Question 1
    Question 2
    Question 3

# hover 
nav li:hover {
	cursor: pointer;
	background-color: #dfdfe2;
	color: #1b1b32;
}

# fix element to the top of viewport
position: fixed;
top:0;

# centering <section>
section {
    width: 80%;
    margin: 0 auto 10px auto;
    max-width: 600px;
}

# To align the input boxes with each other, set the display property to inline-block
.info input, 
.info label {
  display: inline-block;
  text-align: right;
}

# to neaten block element
text-align: left;
display: block;
width: 100%;
margin-top: 20px;
padding-top: 5px;

# smooth jump to the section
    - The media query prefers-reduced-motion is used to detect if the user has set an operating system preference to minimize the amount of animation or motion it uses. It can take two possible values: no-preference : Indicates that the user has made no preference in the underlying operating system.
    - for users who prefer less motion on web, such as autoplaying videos or some visual effects
@media (prefers-reduced-motion: no-preference){
  * {
  scroll-behavior: smooth;
    }
}

# hide texts for screen reader using aria-hidden
<div id='years' aria-hidden='true'></div> 

# The caption element should always be the first child of a table, but can be positioned with the caption-side CSS property.
<table>
    <caption>Assets</caption>
 </table>

# The thead and tbody elements are used to indicate which portion of your table is the header, and which portion contains the primary data or content.
    <table>
        <caption>Assets</caption>
            <thead></thead>
            <tbody></tbody>
    </table>

# setting box-sizing: border-box;
    - to fit the child element to its parent element
    - even setting padding to the child element, it will not take spaces outside of its parents element.
    https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing

    html {
        box-sizing: border-box;
    }

# selector that selects <span> elements whose class includes 'sr-only'
span[class~='sr-only'] {
  border: 0;
}

# common code to hide screan read texts
span[class~="sr-only"] {
  border: 0 !important;
  clip: rect(1px, 1px, 1px, 1px) !important;
  clip-path: inset(50%) !important;
  -webkit-clip-path: inset(50%)!important;
  height: 1px !important;
  width: 1px !important;
  /* to prevent overflowing */
    overflow: hidden !important; 
    white-space: nowrap !important;
   /*  take these hidden elements out of the document flow. */
    position: absolute !important;
    padding: 0 !important;
    margin: -1px !important;
}
-  overflow:hidden; this property will hide any element that is pushed outside the set width value of selected element with @media.
- clip-path: creates a clipping region that sets what part of an element should be shown. Parts that are inside the region are shown, while those outside are hidden
- -webkit: for rendering content in Safari and Chrome browsers. Webkit code may need to be added in CSS to ensure it renders correctly on Chrome and Safari due to the lack of cross-compatibility.

- use span[class] syntax will target any span element that has a class attribute set, regardless of the attribute's value.
- use !important to ensure this code is applied regardless of specificity.
# reverse the order of nested element <span class='flex'>
h1 .flex {
  display: flex;
  flex-direction: column-reverse;
  gap: 1rem;
}

# :first-of-type pseudo-selector is used to target the first element that matches the selector.
# :last-of-type pseudo-selector is used to target the last element that matches the selector.
h1 .flex span:first-of-type {
  font-size: 0.7em;
}

# stick element
#years {
  display: flex;
  justify-content: flex-end;
  position: sticky;
  top: 0;
}

# z-index specifies an order of elements
    - z-index is used to create layers in css
    - the higher z-index value will place an element on top of the lower value element
        - to posision bg element behind the other element, do
            bg {
                position: absolute;
                z-index: -1;
            }
        - to position element on top of the others, set z-index:1;
    https://www.w3schools.com/cssref/playdemo.asp?filename=playcss_z-index

# fix width of elements; otherwise the width will allow elements to shrink the container because you are using flexbox.
body td {
  width: 100vw;
  min-width: 4rem;
  max-width: 4rem;

}

# :nth-of-type() pseudo-selector is used to target specific elements based on their order among siblings of the same type.
tr.total td:nth-of-type(3) {
  padding-right: 0.5rem;
}

# absolute: to position elements and allows you to adjust it relative to its container.
# you can set elements top, bottom, left, right
    bg {
        position: absolute;
        top:0;
        left:0;
    }

# ::before, ::after
    - put elements before and after the selected elements
    - use 'content' to specify the element you want to put
    <ex>
    HTML:
    <p> Before the text </p><br>
    <p> After the text </p>

    CSS:
    p::before, p::after {
        content:"YAHOO!!! "
    }

    Output:
    YAHOO!!! Before the text
    After the text YAHOO!!! 

# element needs its parent to have a position set as a point of reference when it uses position. 
    
-------------------------------- CSS for Form Practice -------------------------------------

body {
  width: 100%;
  height: 100vh;
  margin: 0;
  background-color: #1b1b32;
	color: #f5f6f7;
  font-family: Tahoma;
	font-size: 16px;
}

h1, p {
  margin: 1em auto;
  text-align: center;
}

form {
  width: 60vw;
	max-width: 500px;
	min-width: 300px;
	margin: 0 auto;
  padding-bottom: 2em;
}

fieldset {
  border: none;
	padding: 2rem 0;
}

fieldset:not(:last-of-type) {
  border-bottom: 3px solid #3b3b4f;
}

label {
  display: block;
	margin: 0.5rem 0;
}

input,
textarea,
select {
  margin: 10px 0 0 0;
	width: 100%;
  min-height: 2em;
}

input, textarea {
  background-color: #0a0a23;
  border: 1px solid #0a0a23;
  color: #ffffff;
}

.inline {
  width: unset;
  margin: 0 0.5em 0 0;
  vertical-align: middle;
}

input[type="submit"] {
  display: block;
  width: 60%;
  margin: 1em auto;
  height: 2em;
  font-size: 1.1rem;
  background-color: #3b3b4f;
  border-color: white;
  min-width: 300px;
}

input[type="file"] {
  padding: 1px 2px;
}
