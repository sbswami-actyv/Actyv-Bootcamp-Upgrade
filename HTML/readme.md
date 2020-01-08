
![enter image description here](https://www.theprimacy.com/blog/wp-content/uploads/2016/10/HTML5.png)



# HTML
HTML stands for Hyper Text Markup Language.
HTML is the standard markup language for Web pages by which you can creat your own webpages. Basically a web page consits of small units called elements that elements are actualy HTML elements . For example Button, Input box, Header, footer etc.
Have look on this image of web page this is including a heading in big letters and normal paragraph. So basicaly it is rendering a H1 tag for cretaing big sentence and P tag for paragraphs

![enter image description here](https://www.w3schools.com/html/img_chrome.png)

Have a look on code for this page . Do not worry if you are not getting it we go to basics and then we look deep inside. Just look the structure only.

for example : 

     <!DOCTYPE html>  
     <html>  
     
      <head>  
       <title>Page Title</title>  
      </head>  
      
      <body> 
        <h1>My First Heading</h1>  
        <p>My first paragraph.</p>  
      </body>  
    
    </html>

Now let us understand each line : 

     <!DOCTYPE html>          // This tells browser that content is HTML
      <html>                  // This is wrapper inside which we write HTML element
        
        <head>                         // Head tag containing basic info abaut page
          <title>Page Title</title>    // tells title
        </head>                        //Head tag closing here
       
        <body>            // Body tag which contains main stuffs to make web pages
          <h1>My First Heading</h1>  // H1  tag for wrriting header of paragraphs 
          <p>My first paragraph.</p>  // P tag for wrinting paragraphs
        </body>           // Body wrapper closing
         
      </html>             //HTML wrapper closing


#  Basic Keys  in HTML

## Elements or Tags: 
Elements are smaller units of HTML for creating web pages. 
Here are some following elements which creates the web page for example input element header element, Footer elements, Button elements.
Following are some HTML tags :


    <a>           It is termed as anchor tag and it creates a hyperlink or link.
    <b>           It is used to make a text bold.
    <button>      it is used to create buttons
    <h1> to <h6>  It will create bigger letters words mostly for creating content headings
    <img>         It is used to insert an image within an HTML document.
    <input>       It defines an input field within an HTML form.
    <h1> - <h6>   Heading
    <p>           Paragraph
    <i> or <em>   Italic / Emphasis
    <b>           Bold
    <ul> & <li>   Unordered List & List Item
    <hr>          Horizontal line
    <div>         Mostly it works as wrapper.  We can create diffrent divisions by wrapping text images and buttons or more elements.
 

## Block Elements Vs Inline Elements: 
**Block** Elements are those Elments which takes full width on screen. No any other tag can be put inside block tag in same line. As shown in figure.
Example :  div, P, h1-h6,header, footer

**Inline** Elements are those elements which do not take full width. As shown in figure
Example : span, input, button.

![enter image description here](https://miro.medium.com/max/2800/1*AFeOAqXNJJdfYAjfXiJ9AQ.jpeg)


##   BOX MODEL

> (Let us understand how the "Briks" of a house behaves ) :

 Let us assum Bricks are HTML ELEMENTS and House is web Page.
Building block of of your house are "Briks". Similarly Building block of the what you see in app HTML elements. As you know some briks are having borders also and some briks are having some texts inside the border. Distance between the border and the text is call padiing. Now border is the ending no any material is available outside of the border of the briks. Now how much space it wants to take even after it is stable and fixed. Means if you are in you office the you create a distance betwwen other employess to sit similary that outer space after the border is called margin

![enter image description here](https://cdn.pixabay.com/photo/2016/01/03/09/58/red-1119245_1280.jpg )

**Border**:  Bulged out area  which is wrapping the letter and crator
**Content** : Letter in the brik
**Padding**: Space Between Letter and border . From area where crator ends and border starts to the area where it touching the letter
**Margin** is the space around the brick  or outer area . See down side the brick, margin is zero for brick because It is totally touching the next three  down side brick without any space. So margin Bottom is 0 .  Margin top is some 5 or 6 units because there is some sapce between two briks on upper side
 No similarly compare this Brick to any HTML element. It will behave same as brick.

  ![enter image description here](https://www.websitenero.com/application/assets/img/html-module/box-model.png )

Increase in padding will increase the width and height because it will create space for inner text of the briks. Increasing the margin will not increase height and width but it will increase the sourounding space. So the bricks have lot of space get reserved for there outer surface.

## Structure Of Elements  

Now if you have to write any tages or elements then tag will have opening representation and closing representation . See in following figure.

![enter image description here](https://www.oreilly.com/library/view/learning-web-design/9781449337513/httpatomoreillycomsourceoreillyimages2257977.png)

Let suppose if we have to use 'h1' tag then we have  write opening tag by writing  `<h1>` and then we have to close it by writing a slash `</h1>`. if we have to put or content in this to display  the we will put inside opening and closing of the tag.











