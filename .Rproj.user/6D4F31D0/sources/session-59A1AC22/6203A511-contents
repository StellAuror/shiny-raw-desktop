# How to import packages listed in req.txt
req <- scan(file.path(dirname(getwd()), "req.txt"), character(), quiet = T)
invisible(lapply(req, library, character.only = T))

library(shiny)
library(shinyWidgets)
library(shinyalert)
library(htmlwidgets)
library(bs4Dash)
library(waiter)
library(tidyverse)
library(echarts4r)
library(plotly)
library(lubridate)
library(DT)
library(reactable)
library(reactablefmtr)
library(esquisse)

shinyApp(
  ui = bs4DashPage(
    title = "3Art",
    fullscreen = T,
    scrollToTop = T,
    dark = NULL,
#### BODY ####
    body = bs4DashBody(
      includeCSS("page.css"),
      tabItems(
        tabItem(
          tabName = "newt",
          renderUI("newt.datebar"),
          # Esquisee content
          esquisse_ui(
            id = "esquisse", 
            header = FALSE 
          )
        )
      )
    ),
#### SIDEBAR ####
    sidebar = bs4DashSidebar(
      collapsed = T,
      minified = T,
      elevation = 5,
      fixed = T,
      expandOnHover = F,
      sidebarMenu(
        id = "sidebar.main",
        menuItem(
          text = "New Training", tabName = "newt",
          icon = icon("compass")
        ),
        menuItem(
          text = "Data", tabName = "data",
          icon = icon("cogs"),
          badgeLabel = "loaded",
          badgeColor = "success"
        ),
        menuItem(
          text = "Filter", tabName = "filter",
          icon = icon("filter")
        )
      )
    ),
#### HEADER ####
    header = bs4DashNavbar(
      
    ),
#### CONTROLBAR ####
    control = bs4DashControlbar(
      
    )
  ),
#### SERVER ####
  server = function(output, input, session) {
    
    ### Esquisee
    data_r <- reactiveValues(data = iris, name = "iris")
    results <- esquisse_server(
      id = "esquisse",
      data_rv = data_r
    )
    
    ### Make sure to close session
    session$onSessionEnded(function() {
      stopApp()
    })
  } 
)
