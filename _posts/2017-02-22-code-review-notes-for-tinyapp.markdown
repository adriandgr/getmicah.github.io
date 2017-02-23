---
title: Code review notes for TinyApp
date: 2017-02-22 16:22:00 -08:00
layout: post
---

<img src="/uploads/kortos.jpg" width="800px">

Code review for tinyApp assignment.  

Notes given by Dave during code review:
- use `temp/` directory to store local files instead listing them individually in the `.gitignore` file
- ensure there is a new line character at the end of all code files
- `require('dotenv')` as early as possible
- move dev-dependencies to regular dependencies or guard them while in production mode
- [moment.js](https://momentjs.com/) as an alternative to dateformat
- look into app.listen and server.address api (for reporting the server address) domain configuration should be in `.env` file


ejs, set configuration (not a middleware.
app.set is a configuration

session fixation attacks)


emails may not be validated with regular expression.
falsehoods programmers believe

curated lists of falsehoods
RFC 822 ()

if users()

why return false when you meant undefined

decalre 

give functions properties

do {} while

do conditonals

res.locals >>> read more about. use 
If user simplification

cyclomatic complexities... use return, use guards.

opening cur

what is somebody's username is urls....

bithound.... static code analysis

sonarqube, code quality tool

first, check if exists.
if it doesn't exist 404
ntp drift


should only delete if user is owner

401 on POST /urls

keep them at the top (the guards)

avoid for ( in loops)

always test for the true value.




check valid scheme such as ftp