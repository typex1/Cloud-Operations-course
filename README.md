# Cloud-Operations-course

### Question: How to create an ec2 instance that uses instance store?

### Answer:

To create an EC2 instance that uses instance store, you'll need to follow a series of steps in the AWS Management Console. Here's a guide to help you through the process:

1. **Prepare for Instance Launch**
   - Sign in to the AWS Management Console
   - Navigate to the EC2 dashboard at https://console.aws.amazon.com/ec2/
   - Ensure you're in the correct region (currently eu-north-1)

2. **Start the Instance Launch Wizard**
   - Click on "Launch Instance" button in the EC2 dashboard

3. **Choose an Amazon Machine Image (AMI)**
   - Select an AMI that supports instance store volumes
   - Note that not all instance types support instance store, so choose carefully

4. **Select an Instance Type**
   - Choose an instance type that supports instance store volumes -> The following instances support instance store volumes that use non-NVMe SSDs to deliver high random I/O performance: C3, I2, M3, R3, and X1. 
   - Pay attention to the instance store capacity listed for each type

5. **Configure Instance Details**
   - Set the number of instances and other network settings as needed
   - No special configuration is needed for instance store at this step

6. **Add Storage**
   - In the "Add Storage" section, you'll see the available instance store volumes
   - These volumes are automatically attached and don't require manual configuration -> mount target is /mnt
   - Note that the number and size of instance store volumes depend on the instance type

7. **Add Tags (Optional)**
   - Add any tags you want to associate with your instance

8. **Configure Security Group**
   - Set up a security group to control inbound and outbound traffic

9. **Review and Launch**
   - Review your instance configuration
   - Click "Launch" when you're ready

10. **Select or Create a Key Pair**
    - Choose an existing key pair or create a new one
    - This is crucial for securely accessing your instance

11. **Launch the Instance**
    - Confirm and launch your instance

12. **Access and Initialize the Instance Store**
    - Once the instance is running, connect to it
    - The instance store volumes will need to be formatted and mounted before use
    - Use appropriate commands based on your operating system to format and mount the volumes

Remember, instance store provides temporary block-level storage. The data on instance store volumes persists only during the life of the associated instance. For any data that needs to persist, consider using Amazon EBS volumes instead.

Always follow security best practices when setting up your EC2 instances, including using the principle of least privilege for IAM roles and security groups. Test your setup in a non-production environment before deploying to production.

By following these steps, you'll have successfully created an EC2 instance that uses instance store for temporary, high-performance block-level storage.

Sources:

[1] [Add instance store volumes to an EC2 instance - Amazon Elastic Compute Cloud] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/add-instance-store-volumes.html)

[3] [Add instance store volumes to an EC2 instance during launch - Amazon Elastic Compute Cloud] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/adding-instance-storage-instance.html)

[6] [Instance store temporary block storage for EC2 instances - Amazon Elastic Compute Cloud] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)
