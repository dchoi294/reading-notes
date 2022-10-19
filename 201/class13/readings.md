# Class13 Reading Notes

1. Why would a developer use local storage for a web application?

- *"The main problem with HTTP as the main transport layer of the Web is that it is stateless."* This means taht it doesn't automatically save what you have been working on when you close an application on your desktop. But, local storage solves this problem by keeping a key on the user's computer and read it out when the user returns.

2. What information should not be stored in local storage?

- sensitive information such as passwords or personal information.

3. Local storage can store what type of data? How would you convert it to that type before storing?

- String data, and there are two ways to convert the other type to string by implicit and explicit(JSON.stringify() or JSON.parse()).

Reference [Local Storage and How To Use It On Websites](https://www.smashingmagazine.com/2010/10/local-storage-and-how-to-use-it/)  

## Things I want to know more about

More details about what local storage can do other than saving data and display it when I need it.

[Back to Home](../../README.md)
