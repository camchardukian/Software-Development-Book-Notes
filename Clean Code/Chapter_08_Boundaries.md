# Chapter 8 -- Boundaries

## Using Third-Party Code

There's a natural conflict that occurs between providers of third-party packages and users.
Providers want their package to have broad appeal and to be able to work in many environments while users want a solution that is focused on their particular needs.
It's important to be mindful of the issues this can cause.

## Exploring and Learning Boundaries

While doing so isn't our job, it may be in our best interest to write tests for the third-party code we use.

## Learning Tests Are Better Than Free

Writing tests to learn about how third-party code works doesn't cause us to incur any additional costs. We were going to have spend time to learn how the third-party code worked anyway.
An additional benefit of writing these tests, however, is that whenever there are new releases of the third-party packages we can run our "learning tests" to see whether the new versions have any behavioral differences and whether there are any incompatibilities with how we are currently using the package(s) in our app.

## Clean Boundaries

Because third-party code is not under our control, we must be extra mindful in how we intend to use third-party code when designing a system.
