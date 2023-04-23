## R Shiny App as a standalone desktop application

Great workaround to run application in local browser.

## App structure

- app - the actual application (R code)

- req.txt - libraries required to run app (for R kernel)

- R - contains R kernel (R code in interpreted every time app is being launched) & libraries mentioned in req.txt

- chrome - portable version of Google Chrome browser, not used

- run.R - R code needed to run local host

- run /.txt/.bat/.exe - piece of code needed to run app

- Icon - app icon

## Original repo

[GitHub - derryleng/Shiny_Desktop_App: Quick and simple guide to packaging R Shiny applications as a standalone Windows desktop program.](https://github.com/derryleng/Shiny_Desktop_App)
