
# UNIT 3 FINAL: PART ONE

In this part, you will be given code snippets and asked questions about those snippets. Feel free to run this code in the linked environments to help debug the issues. 

## 👉👉 README CAREFULLY BEFORE CONTINUING! 👈👈

For each problem below, there will be starting code linked in a **REPL.it** snippet. Feel free to play around / debug in that snippet. Once you are happy with your solution, copy/paste your solution to a file named **exactly** what is requested in the problem.

Each problem will require a corresponding **problem_1.js**, **problem_2.js**, etc. To submit Part One, zip up your 4 solution files and upload to canvas. (Problem 4 will need a folder on it's own)

## Problem 1

Add the following 2 routes to **[this express server](https://repl.it/@mottaquikarim/AvariciousWelcomeField):

### GET /time
Returns JSON that looks like this:

```
{
  "time": "Wed Jan 23 2019 21:03:06 GMT-0500 (Eastern Standard Time)"
}
```

### GET /greet/:name

Returns JSON that looks like this:

```
{
  "greeting": "Hello Mo!"
}
```

(if someone made a GET request to `/greet/Mo`).

Copy and paste your solution from `index.js` in the **REPL** snippet into a file called **problem_1.js**. **THIS IS YOUR SOLLUTION TO THIS PROBLEM**.

## Problem 2

Add `body-parser` middleware (already required) in the appropriate spot in **[this express server](https://repl.it/@mottaquikarim/MealyDarkseagreenEngine)** to ensure POST body content can be adequately sent to the server.

**SUPPORT BOTH FORM-ENCODED AND JSON POST BODYs**

Copy and paste your solution from `index.js` in the **REPL** snippet into a file called **problem_2.js**. **THIS IS YOUR SOLLUTION TO THIS PROBLEM**.

### Resources

To test, you can **cURL**:

```
$ curl -X POST ${YOUR_REPL_URL}/user
```

Be sure to swap the `${YOUR_REPL_URL}` to whatever is on the righthand side of your screen. For the response above, you want to get back a JSON response.

## Problem 3

The `user` routes for **[this express server](https://repl.it/@mottaquikarim/WindingNativeDatamart)** are not working! Implement a fix to ensure this works. Be sure to note the `user.js` file on the snippet above.

Copy and paste your solution from **`user.js`** in the **REPL** snippet into a file called **problem_3.js**. **THIS IS YOUR SOLLUTION TO THIS PROBLEM**.


### Resources

To test, you can **cURL**:

```
$ curl -X POST ${YOUR_REPL_URL}/user
$ curl -X GET ${YOUR_REPL_URL}/user/1
$ curl -X PUT ${YOUR_REPL_URL}/user/1
$ curl -X DELETE ${YOUR_REPL_URL}/user/1
```

Be sure to swap the `${YOUR_REPL_URL}` to whatever is on the righthand side of your screen. For all responses, you *want*: `{"success": true,}`

## Problem 4

Given an authenticator middleware, lock down the routes in **[this express server](https://repl.it/@mottaquikarim/ExcitingOffensiveEllipse)** to ensure they cannot be access publicly.

This problem may require changes to multiple pages - copy and paste the content of the files that you changed into a **folder** called **problem_4**. **THIS IS YOUR SOLLUTION TO THIS PROBLEM**.

### Resources

To test, you can **cURL**:

```
$ curl -X POST ${YOUR_REPL_URL}/user
```
Expect 403

```
$ curl -X POST ${YOUR_REPL_URL}/user -H "Token: test"
```
Expect `{"success": true,}`

```
$ curl -X POST ${YOUR_REPL_URL}/post
```
Expect 403

```
$ curl -X POST ${YOUR_REPL_URL}/post -H "Token: test"
```
Expect `{"success": true,}`

etc
