# knowbi-pentaho-deploy
This repository contains Pentaho Data Integration (PDI, aka Kettle) Jobs and Transformations to deploy from version control (VCS) to your Pentaho BA server(s).
All BA content will be managed in and deployed from your VCS.
This solution covers: connections, mondrian schemas, content (eg. public/customerX/report.prpt) and ACLs.
 
The main job expects a single input parameter, PRM_ENV and there are 5 properties file that drive the solution:
- content: defines where the content is stored
- content.permissions: defines the ACLs that need to be defined
- general: defines the pentaho server where we will deploy to
- jdbc: defines the JDBC connections that will be created
- mondrian: defines where the mondrian schemas are stored and which connections they will be using
 
The PRM_ENV parameter defines which properties files are being used to configure the solution
deploy.content.${PRM_ENV}.properties
deploy.content.permissions.${PRM_ENV}.properties
deploy.general.${PRM_ENV}.properties
deploy.jdbc.${PRM_ENV}.properties
deploy.mondrian.${PRM_ENV}.properties
 
The solution main job is jb_pentaho_deploy.kjb and all sub Jobs and Tranformations are stored in the pdi folder.
