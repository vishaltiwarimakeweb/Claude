# Instructions for the App

- This is a Next.js full stack task-management application.

- Tech Stack : React, Next.js, Typescript, MongoDB, Mongoose, Tailwind CSS, Next.js API Router, Next.js App Router.

## Architecture :

/src
proxy.ts --> A middleware to stop not logged in users to visit protected route and logged in users to visit auth routes.
/app /
/api --> For all the backend requests (/auth/login, task/[taskId] etc.)
/components --> Reusable cards and small UI blocks such as Task card etc.
/model --> Contains mongo db schema
/lib --> SDKs and instances
/context --> All contexts for Context API
/utils --> Small helping functions
error.tsx --> Error page
not-found.tsx --> For incorrect route visiting

## Features

### Auth :

- Secure auth using JWT and Bcrypt password hashing.

- Tasks CRUD.

- Strict email regex verification.

- Minimum 8 length password (after trimming spaces).

- Registering includes mandatory details like Name, unique email & password but non-mandatory details like age, profile avatar.

- Firstly check if the email is registered or not, if not send appropriate response, only then check whether the entered password matches the credentials or not.

- Secure OTP based password reset if forgotten by sending the 5 digit OTP to the user's email by using Brevo.

### Tasks :

- Task have a mandatory title of length 5 and optional features such as description, deadline.

- Default properties which can be changed by the user during or anytime after task creation : Status ( To Do by default ) and Priority ( Medium by default ).

- Task filtering by searching keyword that matches task's title or description. Filtering by status and priority.

- Marker at every task card according to the task's deadline. If deadline doesn't exist, don't show any marker,but show Plenty of time (if deadline > 10 days ), approaching (if deadline > 6) & critical (if deadline < 3 days).

- Pagination of 10 tasks per page with disabled previous or next buttons for unavailable pages.

### Profile :

- View, Edit & Delete profile features.

- Password changing requires entering current password or verifying user's credbility by entering correct 5 digits OTP sent to the registered email by Brevo.

## GENERAL INSTRUCTIONS AND CONVENTIONS :

- Use proxy.ts middleware to stop users from visiting unauthorized routes.

- Use vitest for testing.

- Always use Typescript to ensure strict types.

- Avoid using any type as much as possible.

- In case of vague requirements, ask for the crucial details.

- Always use httpOnly cookies, with secure : true & sameSite : "lax".

- Use npm install( install command ), npm run build( build command ), npm run dev ( for starting the app ) & npm test ( for testing ).

- Use Tailwind CSS to toggle dark/light UI modes.

- Before implementing anything, write a plan, analyze edge cases and after successful verfication, proceed.

- Only change the necessary files for a task.

- Keep the folder structure manageable, avoid over-engineering and too many modules.

- Use MVC structure.

- Always follow failure tests before implementing any feature.

- Make sure to perform regression tests to fix a bug.

- Don't bypass edge cases just to pass the tests, if some cases fail, follow a new approach so that it doesn't.

- Keep the UI modern and eye - catching.

- Send all the API requests to /api/...

- Use Next.js API Routes for all the backend requests.

## Defintions of Done :

- Any task can be marked as done if it verifies all the required tests. ( Failure tests for new features and regression tests for bugs ).
- Can do the desired action as requested by the user.

## Github Workflow :

- For every feature, create a new feature branch, add commit with appropriate message and create a pull request.
