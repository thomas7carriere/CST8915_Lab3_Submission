# CST8915_Lab3_Submission

I created three new repositories for the Product-Service, Order-Service and Store-Front as the previous lab hasn't been graded yet and didn't want to affect it.

- Product-Service: https://github.com/thomas7carriere/CST8915_Lab3_Product_Service
- Order-Service: https://github.com/thomas7carriere/CST8915_Lab3_Order_Service
- Store-Front: https://github.com/thomas7carriere/CST8915_Lab3_Store_Front

- Video Demo: https://youtu.be/gJij8g5vp9Q

Reflection Questions:

- What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?
- The change to configuing environment variables for the Store-Front using in the GitHub Actions Workflow was much the same as how they were hard-coded in lab1. In my opinion, it's not as clean as how it was done using .env files or the Azure App Environment variables, as they are still available to the public. Perhaps GitHub secrets would be a good next step to hide congifuration details.
  
- How does deploying microservices on Azure Web App Service differ from running them locally?
- Azure Web App Services is a PaaS service, meaning the configuration of the runtime environment is handled for us. This is a stark difference compared to Labs 1 and 2 where the environment had to be manually set-up in the virtual machines. Also, all the infrastructure is handled by Azure, with the added benefits of scaling and availability that our local hosting would not be able to offer out of the box.
  
- Why is it important to use environment variables for configurations in a cloud environment?
- It follows the 12-Factor app for creating cloud friendly applications. Removes the need for hard-coding variables in the environment, which poses security and maintainability issues. Also allows us to configure different configuration details depending on whether we are deploying for development or production for example.

Challenges: I had forgotten to add an inbound port rule on the NSG of the RabbitMQ VM for Port 5672, which stopped the order-service and RabbitMQ from being able to communicate. I also chose Python 3.14 as the run-time stack for Produce-Service App. This caused issues as I had dependencies that were not yet supported by 3.14, so in the GitHub action I had to change a release value to 3.11.
