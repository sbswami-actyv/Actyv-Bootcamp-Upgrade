# REACT
ReactJS is JavaScript library used for building reusable UI components. According to React official documentation, following is the definition −

React is a library for building composable user interfaces. It encourages the creation of reusable UI components, which present data that changes over time. Lots of people use React as the V in MVC. React abstracts away the DOM from you, offering a simpler programming model and better performance. React can also render on the server using Node, and it can power native apps using React Native. React implements one-way reactive data flow, which reduces the boilerplate and is easier to reason about than traditional data binding.

# BASIC  KEYS   IN REACT JS
## COMPONENTS :
Let us take example of an app. If you will see any app then you will see that it is made up of idividual units like buttons, cards, menu etc. if you will see the menu then there will be lot of options will be listed inside the menu in form of smaller cards. So what  you will do?
are you going to create each of the options repeatedly. If you do it will take time and memory as well. Another approach is that we can create one card and we can call it in menu with what amount of number we want. We can pass the diffrent values to that same component wich will behave diffrent with diffrent inputs .
Component is bulding block of the UI, which we can reuse it.

Type of components : 



>> **Functional components:** 
are those components which takes Props or values and return some JSX or HTML Elements .
Basicly it is a function which takes props/values and gives JSX/HTML.

    import React from  'react';
    function  App()  {
      const greeting =  'Hello Function Component!';
      return  <h1>{greeting}</h1>;
    }
    export  default App;=
> >  **Class components:**  
> > are those components which takes Props or values and return some JSX or HTML Elements .  
> > Basicly it is a class which takes props/values and gives JSX/HTML.
> >They are having there states

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

## PROPS :  
As we discussed above, we can pass the values in components so they can give diffrent output.
For example :  In menu's options, the component is same but the name will be diffrent like option1, option2, option3, etc. but shape size will be same.
So, how it is changing the name only but shape and size is common. This is what is called Prop.
We have to pass the values to components so it can show the name or any other values . The values which we pass to component, are called Props

    <option> <option/>                      //this is option component
    <option name = "option1"> <option/>     //this is component with props

In followind example the option component will show its name as option1. Because we have passed props to component. You can also say that you are paasing some values to component.

## STATE  :
 State is that variable of component on which behaviour of component is decided.
Supose we have to change the color of the component then there should be a variable which is dirctly connected to the components behavour. If we will change the value that variable then color will be get changed.
How it is diffrent from normal variable ?]
State behaves as live variable . when the state will be get changed we dont have to again give the comand to change the behaviour. It is directly subscribed to the component

Points to be noted : 
1: State is immutable . Use setState() method to change the state

## FRAGMENTS:
 In react you can not render more then one component or element  in rendor function. You have to wrap all the component in a single element. But it will show the wrapper element as well.
if we want to wrap up the element so it will not be counted on dom, we can use Fragments
 
 
     *****Wrong CODE******
     
     rendor(
        return(
           <p>line one</p> . // 1st element
           <p>line one</p> . // 2nd element
          )
        )
    
  upper code wrong  in one time we can use one componet to render but two 
  "< p > < /p >" component is loading which returns error

    *****Right Code******
    
         rendor(
            return(
            <div>
               <p>line one</p> . // 1st element
               <p>line one</p> . // 2nd element
            <div>
              )
            )
this is right code in which we wrapping the 'P' elements/tag/components  in a single "div" 

now the best  code is that which uses Fragments

    *****Best Code******
        
             rendor(
                return(
                <Fragments>
                   <p>line one</p> . // 1st element
                   <p>line one</p> . // 2nd element
                <Fragments>
                  )
                )
this will not show the fragment when it is mounted it will show only two wrapped components. No any extra div will be there for formality.

## Lifecycle of a component
when you open any app then you loads the components and when you switch to another page those components get removed. So these thing happens with the component.
1: Mount
2: Update
3: Unmount

Now let just chek what methods react js giving for lifcycle of components and why !

-   **componentWillMount**  is executed before rendering,
    
-   **componentDidMount**  is executed after the first render only on the client side. This is where AJAX requests and DOM or state updates should occur. This method is also used for integration with other JavaScript frameworks and any functions with delayed execution such as  **setTimeout**  or  **setInterval**. We are using it to update the state so we can trigger the other lifecycle methods.
    
    
-   **shouldComponentUpdate**  should return  **true**  or  **false**  value. This will determine if the component will be updated or not. This is set to  **true**  by default. If you are sure that the component doesn't need to render after  **state**  or  **props**  are updated, you can return  **false**  value.
    
-   **componentWillUpdate**  is called just before rendering.
    
-   **componentDidUpdate**  is called just after rendering.
    
-   **componentWillUnmount**  is called after the component is unmounted from the dom. We are unmounting our component in  **main.js**. 

## LIST HANDELING
If we use to display list then in react we have to awair about thee fact that react should have to know the changes in component. If react is not getting the  differnce in list items then it will give unwanted list.
So in react we have to use key , so react can distinguish between the list items because key will be uniqe.
Do not use indexes as  key .

    number.map( element => {
    return <Li key={number.toString()} value={number}  />  // defining key
    } )
    
##  WHAT is "Ref"
If you have to select element on dom then there are 3 famous querry function to serach the  element. 
1: document.getElementById()
2: document.getElementsBytagName()
3:document.getElementsByClassName()

But in react you right the UI code in JSX and that JSX rendered as HTML element so you should not have to use these functions because react will not know the changes.
so we can use Ref to slect the elements and change the value.

Refs are created using `React.createRef()` and attached to React elements via the `ref` attribute.
```
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.myRef = React.createRef();     // here we are defining ref
  }
  render() {
    return <input ref={this.myRef} />;   // here we are putting ref to select elemnt
  }
}

```
Now if we want to access the value of input box then we can acces it by using  
```
 this.myRef.current;   // it will select the input box 
 this.myRef.current.value;  // it will show the value of input box 
```

   

## Error Boundries
Error Boundries are react component that captures error and shows a fallback UI. It is done  by using getDerivedStateFromError(error) or componentDidCatch(Error) by changing the state to show fallback UI

   ```
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    // Update state so the next render will show the fallback UI.
    return { hasError: true };
  }

  render() {
    if (this.state.hasError) {
      // You can render any custom fallback UI
      return <h1>Something went wrong.</h1>;
    }

    return this.props.children; 
  }
}
```

## Passing Props From parent to child : 
To pass props in child component, We can directly pass it where component is called.
 
      <div>
      <Greeting  color={green}  /> passing prop/data color as green
      </div>
 Now we have to recive it where we have defined the componet 


    import React,  { Component }  from  'react';
    class  App  extends  Component  {
      render(props)  {               // reciving props
      return  (
      <div>
      <h1>{props.greeting}</h1>     // using prop value to display
      </div>
      );
      }
    }
    export  default App;

## Passing Props From child to parent : 

To pass props from parent to child is too easy . but there is no any portal looks to pass some data from child to parent.because when we call the element or component then we can pass the data but we cannot send data from where it is defined.
Bu we can do it by passing callback function from parent to child and passing the data and running the callback function from the child component .
   

        import ChildComponent frm ".../location"
        class SomeParentComponent extends React.Component {
          constructor(props) 
           { super(props); 
             this.state = {color: 'red'}; 
           }
          function recieveDataAndChangeColor(data) {
            this.setState(
              {
               color : data
              }
            )
          }
         render() { 
            return  <ChildComponent color = {this.recieveDataAndChangeColor.bind(this)} />; 
            } 
         }

 Now getting the function and calling it in child component.
 when we call the recieveDataAndChangeColor("green") it will pass the value green from child component  and run the fucntion and fucntion will set state's color as green
 

      class ChildComponent extends React.Component {
           constructor(props) 
            { super(props);
            }
            componentDidMount(){
            this.props.recieveDataAndChangeColor("green")  // calling function here
            }
           render() { 
             return  <p> This is child component <p/>; 
             } 
      }


## Extra Points : 
**How to set default props ?** 
```
class CustomButton extends React.Component {
  // ...
}

CustomButton.defaultProps = {
  color: 'blue'
};
```
**Is react supports bi directional data flow ?** 

Yes. React basicaly provides unidirectional flow . We can pass data from parent to child but we can not directly pass data from child to parent  .We have to  use arrow functions to pass data from child to parent. This can be done by defining a callback function in parent component  and then calling it into child component









