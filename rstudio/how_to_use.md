# How to use PDL rstudio site

## Registration and set up
### Obtain NCSA user account
Since the site is created on NCSA vm, the user must have a NCSA account to use it.
- the maintainer of the site will send a URL to register to the NCSA group
- follow the link and the steps then the maintainer will add the user in the group

### First login to the server
To use the rstudio and shiny site, the user must ssh in to server to create a home directory. 
The home directory will be automatically connected to rstudio
- after obtaining the NCSA user account, use it for logging in to the server.
```
ssh fd-rstudio.ncsa.illinois.edu
```
- linux or Mac users can directly type above command. 
- Windows users need some ssh tool like putty

### Create shiny app folder
To connect the app created from the Rstudio site, the things must be located inside the ShinyApps folder. 
So the folder path will be like this
```angular2svg
/home/userid/ShinyApps
```
This folder can be created by linux command, or can be created using rstudio site.
```angular2svg
mkdir ~/ShinyApps
```
Following command will create a folder and default app 
```angular2svg
mkdir ~/ShinyApps
cat << EOF > ~/ShinyApps/app.R
library(shiny)

# Define UI for miles per gallon app ----
ui <- pageWithSidebar(

  # App title ----
  headerPanel("Miles Per Gallon"),

  # Sidebar panel for inputs ----
  sidebarPanel(),

  # Main panel for displaying outputs ----
  mainPanel()
)

# Define server logic to plot various variables against mpg ----
server <- function(input, output) {

}

shinyApp(ui, server)
EOF
```

## Use the sites
### Rstudio
You can access rstudio site using https://rstudio.ag-r.ncsa.illinois.edu
If you haven't made ShinyApps folder already, you can create it from File->New File menu.
- try to create any project under ShinyApps folder, otherwise, it will not connect to shiny server.
- try to save the project as often as possible since there is no auto save function.

### Shiny
You can access shiny site using https://shiny.ag-r.ncsa.illinois.edu
Your own site will be the combination of 'users' and 'userid'. 
- https://shiny.ag-r.ncsa.illinois.edu/users/userid/

### Installation of the package
- You can install the necessary package using rstudio's install option.
- There are some packages that needs the installation of the library directly into the server as a root.
- In that case, please contact the maintainer to install the necessary library so you can intall the necessary package.

## Other information
### How to set up the site
The detailed process is in here. https://gist.github.com/robkooper/ffc09f85a7dee3bc7b14d6d9e36014da

### Shiny server configuration file
