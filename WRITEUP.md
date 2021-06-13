# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

Based on theory/descriptions in the Cloud Developer using Microsoft Azure Nanodegree Program (e.g. Lesson 2: Azure Compute Services):

#### Evaluating VM
VMs are an IaaS solution. They allow you to fully access and control the VM. You can choose for different types of VM (e.g. compute or memory-optimized VMs, along with varying amounts of CPU, RAM and storage). With VMs, it is possible to group together multiple VMs to provide high availability, scalability, and redundancy. When comparing to App Services, they could be more expensive and they can be more time consuming for the developer to setup. They do, however, provide a greater level of control/flexibility.

#### Evaluating App Service
App Service is the PaaS solution. This means (also compared to VMs) that the developer can focus on the application while Azure takes care of the infrastructure. App Service supports multiple programming languages, has a high availability (vertically and horizontally), auto-scaling, enables for continuous deployment model using GitHub and you can set the amount of hardware allocated to host the application. You must choose a service plan. Comparing to VMs, with App Service you have limited access to the host server (unable to control the underlying OS or install software on server), you will always pay for the service plan (also if the application isn't used or running), there are hardware limitations (14 GB of memory and 4 vCPU cores per instance) and you are restricted to the supported programming languages. 

#### Decision between VM or App Service
While there are clear differences between VMs and App Services, there is some ambiguity/a "grey area". VMs seem to be better when control is needed over the underlying OS or if you are using custom software to support needs. App Services seem to be better for lightweight applications and services (i.e. when there is no need for high performance compute services). It is, however, important to take into account the hardware limitation of App Services. Based on the above similarities and differences, I would decide to use App service for this project. This is the "easier" option and there is no description/evidence that this is a very big application right from the start (further supported by the SQL table). Therefore I would suggest a lightweight application. Also there is no description/evidence that there will be a huge number of users of the app.  

### Assess app changes that would change your decision.
*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

If the App Service needs to be updated to account for more content, features and users, more hardware will be enabled. That will result in more costs (service plan). Also, if more control is needed (not readily supported by Azure), then that cannot be done in App Service because there is no control over the underlying software on the server. In this case, I would consider other alternatives (e.g. VMs). 

When the CMS app becomes even more popular, multiple VMs might be needed. This also leads to added complexity. VMs allow for further control, which means it is also less reproducible and harder for others to understand. Multiple VMs also lead to an increase in costs. In this phase, I would do research in other alternatives (if any). 
