# Sleep Earning

This is a tiny single-file web app that turns a yearly salary into the money you are effectively making while you are out living your life.

The idea behind it is simple: I wanted a playful way to show that we still make money even when we are not at work. A beer with friends, a hike, a nap, a weekend trip, all of it still has a dollar value attached to the time it takes.

## What it does

- Lets you enter a yearly salary.
- Treats that salary as an hourly rate by dividing it by 8,760 hours in a year.
- Uses a simple Massachusetts tax estimate.
- Shows the estimated after-tax income for a few random everyday activities.
- Lets you reshuffle the activities with a button.

## Important assumptions

- Massachusetts is the assumed state for tax.
- The app uses a simple estimate, not a real payroll calculation.
- Federal withholding, deductions, credits, exemptions, and other filing details are not modeled.
- The hourly conversion is intentional and is part of the point of the app.

## How to run it

Open `index.html` in a browser.

## Limits

- The activity list is fixed.
- The tax model is intentionally coarse.
- The numbers are meant to be understandable and fun, not tax advice.
