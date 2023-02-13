# Class 41 Reading Notes

## Dynamic Routes

***Page Path Depends on External Data***

Next.js allows you to statically generate pages with paths that depend on external data. This enables dynamic URLs in Next.js.

![reading41](../image/reading41.png)

```
import Layout from '../../components/layout';

export default function Post() {
  return <Layout>...</Layout>;
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}

export async function getStaticProps({ params }) {
  // Fetch necessary data for the blog post using params.id
}
```

![reading41(2)](../image/reading41(2).png)

***Implement getStaticPaths***

Create a file called [id].js inside the pages/posts directory.
Also, remove first-post.js inside the pages/posts directory — we’ll no longer use this.

```
# lib/posts.js
export function getAllPostIds() {
  const fileNames = fs.readdirSync(postsDirectory);

  // Returns an array that looks like this:
  // [
  //   {
  //     params: {
  //       id: 'ssg-ssr'
  //     }
  //   },
  //   {
  //     params: {
  //       id: 'pre-rendering'
  //     }
  //   }
  // ]
  return fileNames.map((fileName) => {
    return {
      params: {
        id: fileName.replace(/\.md$/, ''),
      },
    };
  });
}

# pages/posts/[id].js
import { getAllPostIds } from '../../lib/posts';

export async function getStaticPaths() {
  const paths = getAllPostIds();
  return {
    paths,
    fallback: false,
  };
}
```

```
#lib/posts.js
export function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`);
  const fileContents = fs.readFileSync(fullPath, 'utf8');

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents);

  // Combine the data with the id
  return {
    id,
    ...matterResult.data,
  };
}

# pages/posts/[id].js
import { getAllPostIds, getPostData } from '../../lib/posts';

export async function getStaticProps({ params }) {
  const postData = getPostData(params.id);
  return {
    props: {
      postData,
    },
  };
}

# pages/posts/[id].js
export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
    </Layout>
  );
}
```

## Deploying Your Next.js App

To push to GitHub, you can run the following commands (replace `<username>` with your GitHub username)

```
git remote add origin https://github.com/<username>/nextjs-blog.git
git push -u origin main
```

Vercel is a serverless platform for static and hybrid applications built to integrate with your headless content, commerce, or database. We make it easy for frontend teams to develop, preview, and ship delightful user experiences, where performance is the default.

 run the build script once, which builds the production application in the .next folder
`npm run build`  

After building, the start script starts a Node.js server that supports hybrid pages, serving both statically generated and server-side rendered pages, and API Routes.
`npm run start`



Reference [Next.js - Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)  
Reference [Next.js - Deployment](https://nextjs.org/learn/basics/deploying-nextjs-app)

## Things I want to know more about

[Back to Home](../../README.md)
