# Route Manager  

<PluginInfo name="client"></PluginInfo>  

## Introduction

The Route Manager is a tool designed to manage the main page routes of the system, supporting both `desktop` and `mobile` platforms. Routes created using the Route Manager are synchronized with the menu display (configurable to remain hidden from the menu). Conversely, menus added through the page menu are also synchronized with the Route Manager list.  

![20250107115449](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20250107115449.png)  

## User Manual  

### Route Types  

The system supports four types of routes:  

- Group (group): Used for managing routes in groups, allowing sub-routes to be included  
- Page (page): Internal system pages  
- Tab (tab): A route type for switching tabs within a page  
- Link (link): Internal or external links that redirect directly to the configured URL  

### Adding Routes  

Click the "Add new" button in the top-right corner to create a new route:  

1. Select the route type (Type)
2. Enter the route title (Title)
3. Choose the route icon (Icon)
4. Configure whether it should be visible in the menu (Show in menu)
5. Set whether to enable page tabs (Enable page tabs)  
6. For the Page type, the system will automatically generate a unique route path (Path)  

![20250124131803](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20250124131803.png)  

### Route Operations  

Each route entry supports the following operations:  

- Add child: Add a sub-route
- Edit: Edit the route configuration
- View: View the route page
- Delete: Delete the rou 

### Batch Operations  

The top toolbar provides the following batch operation functions:  

- Refresh: Refresh the route list
- Delete: Delete selected routes
- Hide in menu: Hide selected routes in the menu 
- Show in menu: Display selected routes in the menu 

### Route Filtering  

Use the "Filter" feature at the top to filter the route list as needed.  

:::info{title=Tip}  
Changes made to route configurations will directly impact the system's navigation menu structure. Please proceed cautiously to ensure the accuracy of the route configurations.  
:::  
