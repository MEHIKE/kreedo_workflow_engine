The Bamboo build plan shares two artefacts (both paths are relative to build working directory)
1) build/kreedo_workflow_engine.war
2) ansible/**.**

The Bamboo deploy project downloads these files (both path are relative to deploy working directory)
1) -> build/kreedo_workflow_engine.war
2) -> ansible/**.**

NB! There is an important assumption that this ansible script makes on the remote node. The remote
node requires a ~/set-coco-env.sh script that exports coco properties as follows:
----------------- ~/set-coco-env.sh ------------------------------
#!/bin/bash
# This script is used by application's running in tomcat.
#It exports database properties to access the "coco" database.
export COCO_JDBC_URL="jdbc:oracle:thin:@...."
export COCO_JDBC_USERNAME="..."
export COCO_JDBC_PASSWORD="..."
--------------------------------------------------------------------