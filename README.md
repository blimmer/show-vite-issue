# Vite `require is not defined` Issue Repro

This repository is a reproduction case for vite issue [todo]().

To reproduce:

1. Clone this repo.
1. Install dependencies (`npm ci`)
1. Start vite (`npm run dev`)

![](https://i.imgur.com/9q10pQI.png)

You'll see the following error in the console:

```
Uncaught ReferenceError: require is not defined
    js entry.js:8
    __require chunk-L26DXZYY.js:12
    <anonymous> react-date-picker:1
```

The require in question is a `css` import from the `react-date-picker` library:

```
require("react-calendar/dist/Calendar.css");
```

Indeed, this isn't getting rewritten by the vite process.
