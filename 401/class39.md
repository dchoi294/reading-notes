# Class 39 Reading Notes

## Next.js

To create a Next.js app, open your terminal, cd into the directory you’d like to create the app in, and run the following command:

```
npx create-next-app@latest nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/learn-starter"

# You now have a new directory called nextjs-blog. Let’s cd into it:

cd nextjs-blog


npm run dev
```

You should see a page like this when you access http://localhost:3000. This is the starter template page which shows some helpful information about Next.js.

- Make sure the Next.js development server is still running.
- Open pages/index.js with your text editor.
- Find the text that says “Welcome to” under the `<h1>` tag and change it to “Learn”.
- Save the file.


Create the posts directory under pages.

Create a file called first-post.js inside the posts directory with the following content:

```
export default function FirstPost() {
  return <h1>First Post</h1>;
}
```

Using `<Link>`  
First, open pages/index.js, and import the Link component from next/link by adding this line at the top:

```
import Link from 'next/link';

#And change to it
<h1 className="title">
  Read <Link href="/posts/first-post">this page!</Link>
</h1>
```

Next, open pages/posts/first-post.js and replace its content with the following:

```
import Link from 'next/link';

export default function FirstPost() {
  return (
    <>
      <h1>First Post</h1>
      <h2>
        <Link href="/">Back to home</Link>
      </h2>
    </>
  );
}
```

Unoptimized Image
With regular HTML, you would add your profile picture as follows:
`<img src="/images/profile.jpg" alt="Your Name" />`

Here's an example using next/image to display our profile picture. The height and width props should be the desired rendering size, with an aspect ratio identical to the source image.

```
import Image from 'next/image';

const YourComponent = () => (
  <Image
    src="/images/profile.jpg" // Route of the image file
    height={144} // Desired size with correct aspect ratio
    width={144} // Desired size with correct aspect ratio
    alt="Your Name"
  />
);
```

Adding Head to first-post.js
We haven't added a `<title>` to our /posts/first-post route. Let's add one.

Open the pages/posts/first-post.js file and add an import for Head from next/head at the beginning of the file:

`import Head from 'next/head';`

Then, update the exported FirstPost component to include the Head component. For now, we‘ll add just the title tag:

```
export default function FirstPost() {
  return (
    <>
      <Head>
        <title>First Post</title>
      </Head>
      <h1>First Post</h1>
      <h2>
        <Link href="/">← Back to home</Link>
      </h2>
    </>
  );
}
```

## React

React context allows us to pass down and use (consume) data in whatever component we need in our React app without using props.

In other words, React context allows us to share data (state) across our components more easily.

React context helps us avoid the problem of props drilling.

Props drilling is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.

```
export default function App({ theme }) {
  return (
    <>
      <Header theme={theme} />
      <Main theme={theme} />
      <Sidebar theme={theme} />
      <Footer theme={theme} />
    </>
  );
}

function Header({ theme }) {
  return (
    <>
      <User theme={theme} />
      <Login theme={theme} />
      <Menu theme={theme} />
    </>
  );
}
```

Looking at the example above, the render props pattern for consuming context may look a bit strange to you.

Another way of consuming context became available in React 16.8 with the arrival of React hooks. We can now consume context with the useContext hook.

```
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="Reed">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  const value = React.useContext(UserContext);  
    
  return <h1>{value}</h1>;
}
```

Reference [NextJs](https://nextjs.org/learn/basics/create-nextjs-app)  
Reference [React Context for Beginners](https://www.freecodecamp.org/news/react-context-for-beginners/)

## Things I want to know more about


[Back to Home](../../README.md)
