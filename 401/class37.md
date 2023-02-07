# Class 36 Reading Notes

## ES6

ECMAScript 2015, also known as ES6, introduced many changes to JavaScript. Here is an overview of some of the most common features and syntactical differences, with comparisons to ES5 where applicable.

**Legend**
Here is a key of most identifier names used throughout this reference.

Variable: x
Object: obj
Array: arr
Function: func
Parameter, method: a, b, c
String: str


Variable declaration - ES6 introduced the let keyword, which allows for block-scoped variables which cannot be hoisted or redeclared.

Constant declaration - ES6 introduced the const keyword, which cannot be redeclared or reassigned, but is not immutable.

Arrow function syntax - The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.

Template literals - Expressions can be embedded in template literal strings.

Implicit returns - The return keyword is implied and can be omitted if using arrow functions without a block body.

## React

React is a JavaScript library, and so we’ll assume you have a basic understanding of the JavaScript language. React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both. We will come back to components in a further section, but if you’re not yet comfortable putting markup in JS, this talk might convince you otherwise.

Unlike browser DOM elements, React elements are plain objects, and are cheap to create. React DOM takes care of updating the DOM to match the React elements.

React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.

You can convert a function component like Clock to a class in five steps:

- Create an ES6 class, with the same name, that extends React.Component.
- Add a single empty method to it called render().
- Move the body of the function into the render() method.
- Replace props with this.props in the render() body.
- Delete the remaining empty function declaration.

```
class Clock extends React.Component {
  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.props.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}
```

Handling events with React elements is very similar to handling events on DOM elements. There are some syntax differences:

React events are named using camelCase, rather than lowercase.
With JSX you pass a function as the event handler, rather than a string.

```
# In HTML
<button onclick="activateLasers()">
  Activate Lasers
</button>

# In React
<button onClick={activateLasers}>
  Activate Lasers
</button>

```

## Tailwindcss

A common reaction to this approach is wondering, “isn’t this just inline styles?” and in some ways it is — you’re applying styles directly to elements instead of assigning them a class name and then styling that class.

But using utility classes has a few important advantages over inline styles:

- Designing with constraints. Using inline styles, every value is a magic number. With utilities, you’re choosing styles from a predefined design system, which makes it much easier to build visually consistent UIs.

- Responsive design. You can’t use media queries in inline styles, but you can use Tailwind’s responsive utilities to build fully responsive interfaces easily.

- Hover, focus, and other states. Inline styles can’t target states like hover or focus, but Tailwind’s state variants make it easy to style those states with utility classes.

## Next.js

Next.js provides a solution to all of the above problems. But more importantly, it puts you and your team in the pit of success when building React applications.

Next.js aims to have best-in-class developer experience and many built-in features, such as:

- An intuitive page-based routing system (with support for dynamic routes)
- Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
- Automatic code splitting for faster page loads
- Client-side routing with optimized prefetching
- Built-in CSS and Sass support, and support for any CSS-in-JS library
- Development environment with Fast Refresh support
- API routes to build API endpoints with Serverless Functions
- Fully extendable

Reference [ES6 Syntax and Feature Overview](https://www.taniarascia.com/es6-syntax-and-feature-overview/)  
Reference [React - Hello World](https://reactjs.org/docs/hello-world.html)  
Reference [React - JSX](https://reactjs.org/docs/introducing-jsx.html)  
Reference [React - Rendering Elements](https://reactjs.org/docs/rendering-elements.html)  
Reference [React - Components & Props](https://reactjs.org/docs/components-and-props.html)  
Reference [React - State & Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)  
Reference [React - Handling Events](https://reactjs.org/docs/handling-events.html)  
Reference [Utility First CSS](https://tailwindcss.com/docs/utility-first)  
Reference [Learn Next.js](https://nextjs.org/learn/basics/create-nextjs-app)  
Reference [Why to use Next.js](https://www.youtube.com/watch?v=rtgbaKBhdkk&ab_channel=LeeRobinson)  

## Things I want to know more about

[Back to Home](../../README.md)
