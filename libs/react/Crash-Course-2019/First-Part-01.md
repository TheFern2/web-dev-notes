## Intro

These notes are part of a free crash course from Programming with Mosh [video](https://youtu.be/Ke90Tje7VS0)

## Setup Environment

- Install Node.js, since we will be using npm for managing packages.
- Install create-react-app

```
npm i -g create-react-app@1.5.2
```

- Install vscode or whatever editor of preference
  - Install Simple React Snippets extension
  - Install Prettier

## Create First React App

Starts at minute 9:25

```
create-react-app react-app
```

```
Success! Created react-app at C:\Users\Me\Documents\Projects\react\react-app  
Inside that directory, you can run several commands:                                   
                                                                                       
  npm start                                                                            
    Starts the development server.                                                     
                                                                                       
  npm run build                                                                        
    Bundles the app into static files for production.                                  
                                                                                       
  npm test                                                                             
    Starts the test runner.                                                            
                                                                                       
  npm run eject                                                                        
    Removes this tool and copies build dependencies, configuration files               
    and scripts into the app directory. If you do this, you can’t go back!             
                                                                                       
We suggest that you begin by typing:                                                   
                                                                                       
  cd react-app                                                                         
  npm start                                                                            
                                                                                       
Happy hacking!                                                                         
```

## Hello World

16:05

> Install React Dev Tools on Chrome



## Components Counter App

24:00

```
npm i bootstrap@4.1.1
```

## First React Component

26:17

## Embedding Expressions

36:00

## Setting Attributes

40:51

## Rendering Classes Dynamically

46:38

## Rendering Lists

51:00

## Conditional Rendering

55:00

This talks about doing if/else to display different things on the dom.

```jsx
  renderTags() {
    if (this.state.tags.length === 0) {
      return <p>There are no tags!</p>;
    } else {
      return (
        <ul>
          {this.state.tags.map(tag => (
            <li key={tag}>{tag}</li>
          ))}
        </ul>
      );
    }
  }
```

```jsx
render() {
    return <React.Fragment>{this.renderTags()}</React.Fragment>;
  }
```

### Logical AND

This conditional statement makes no sense to my python, and java eyes, but if the statement to the left of && is true, the string to the right prints to the dom. I am just going with the flow, but I like things a bit more clear like the renderTags method. In js, boolean statements can also contain non bool types like strings.

```jsx
{ this.state.tags.length === 0 && 'Please create a new tag!'}
```

## Handling Events

1:01:00

```jsx
<button
     onClick={this.handleIncrement}
     className="btn btn-secondary btn-sm"
>
  Increment
</button>
```

## Binding Event Handlers

1:03:57

One way binding each method to the constructor

```jsx
constructor() {
    super(); // calls Component constructor
    this.handleIncrement = this.handleIncrement.bind(this); // binds handle method to this
  }
```

Using the arrow syntax

```jsx
  handleIncrement = () => {
    console.log("Increment Clicked", this);
  };
```

## Updating the State

1:08:36

## What happens when State Changes

1:10:53

```jsx
handleIncrement = () => {
    this.setState({ count: this.state.count + 1 });
  };
```

## Passing Event Arguments

1:13:00

## Summary

1:16:07





