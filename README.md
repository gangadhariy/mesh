__Blue-Green Deployment__
Overview
Blue-green deployment is a strategy for releasing software updates with minimal downtime and risk. It involves maintaining two identical production environments, referred to as "blue" and "green". At any given time, only one of these environments serves live traffic while the other remains idle. The active environment (e.g., blue) handles all user requests, while the inactive environment (e.g., green) receives the updated version of the application.

Purpose
The purpose of blue-green deployment is to enable seamless updates and rollbacks without impacting end users. By switching traffic between the blue and green environments, organizations can release new features or bug fixes with confidence, knowing that they can quickly revert to the previous version if any issues arise.

Key Benefits
Zero Downtime: Users experience no interruptions during deployment since the active environment continues to serve traffic.
Rollback Capability: If the new release introduces critical bugs or performance issues, it's easy to revert to the previous version by switching traffic back to the stable environment.
Testing in Production: By directing a portion of traffic to the green environment before fully transitioning, teams can conduct real-world testing and gather feedback from a subset of users.
Increased Reliability: Blue-green deployment enhances the reliability of the deployment process by reducing the risk of introducing errors that could impact all users simultaneously

Implementation

After installed servicemesh and configured it label the namespace which you want to deploy the apps
do the following

git clone https://github.com/gangadhariy/mesh.git
cd mesh
kubectl apply -f manifest.yaml -n <namespace>
kubectl apply -f gateway.yaml -n <namespace>
kubectl apply -f rule.yaml    -n <namespace>
kubectl apply -f virtualservice.yaml -n <namespace>
then run the following command to deploy 2 apps as blue and green 
