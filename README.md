# About OpenStack
OpenStack is an open-source cloud computing platform that enables the deployment and management of infrastructure as a service (IaaS). It provides a suite of interrelated services to manage computing, storage, and networking resources in a data center. OpenStack allows users to create and manage large groups of virtual private servers in a data center.

# Uses of OpenStack
1. Public and Private Cloud Deployment
2. DevOps
3. Data Processing
4. Web Hosting

# Advantages of OpenStack
**1. Flexibility:** OpenStack can be customized to meet specific needs, making it adaptable for various use cases, from public clouds to private clouds.
**2. Interoperability:** OpenStack supports a range of operating systems and hypervisors, making it compatible with various infrastructures.
**3. Scalability:** Easily scales up or down depending on demand, allowing organizations to handle varying workloads efficiently.

# Install OpenStack 
**Step 1:** Begin by installing the openstack snap
           
           sudo snap install openstack --channel 2024.1/beta

**Step 2:** Use the following code for preparing the machine
          
          sunbeam prepare-node-script


![WhatsApp Image 2024-11-04 at 20 41 15_053f38d9](https://github.com/user-attachments/assets/7f859ee1-7f12-4950-b795-92eb6a91ff6b)


**Step 3:** Deploy the OpenStack cloud using the cluster bootstrap command
          
          sunbeam cluster bootstrap --accept-defaults

![WhatsApp Image 2024-11-04 at 20 41 14_6e2cdf48](https://github.com/user-attachments/assets/4a42987d-ef57-4f10-bd95-50d9b3a86fa2)


**Step 4:** configure it using the following command 

          sunbeam configure --accept-defaults --openrc demo-openrc

![WhatsApp Image 2024-11-04 at 20 41 15_183fa2f1](https://github.com/user-attachments/assets/70db5d97-fa1a-41f2-bfa1-5d1a92d93e4b)


**Step 5:** Launch a VM 

          sunbeam launch ubuntu --name test

**Step 6:** Connect to the VM over SSH using the provided command.

          Launching an OpenStack instance ...
          Access instance with `ssh -i /home/ubuntu/.config/openstack/sunbeam ubuntu@10.20.20.200`




# About Virtual Private Cloud(VPC)
A Virtual Private Cloud (VPC) is a private cloud environment hosted within a public cloud infrastructure. It allows users to create a logically isolated network within a public cloud, enabling greater control over their cloud resources while benefiting from the scalability and cost-effectiveness of a public cloud.

# Importance of a VPC
A VPC is essential for enhancing security, control, and flexibility in your cloud setup. **WITHOUT IT!**   you risk exposing your data to threats and losing the ability to manage your resources effectively.

# Uses of a VPC
**1. Hosting Web Applications**

**2. Hosting Web Applications**

**3. Disaster Recovery**

# How to set up your VPC 
**STEP 1:**  To set up your VPC firstly login your AWS account and navigate to VPC Dashboard.

**STEP 2:**  Create your VPC and define your configuration

**STEP 3:**  Create subnets 

To create a subnet:

   * In the VPC Dashboard, click on Subnets in the left sidebar.
   * Click Create subnet.
   * Choose the VPC you just created.
   * Specify a subnet name, Availability Zone (you can select different AZs to ensure high availability), and CIDR block for the subnet (e.g., 10.0.1.0/24 for a subnet in the range 10.0.0.0/16).

**STEP 4:** Set Up Route Tables

1. After creating subnets, you need to configure the route table for your VPC. This defines how traffic is routed within the VPC and to the internet.

2. Go to Route Tables in the VPC Dashboard.

3. Click Create Route Table, name it (e.g., "Public Route Table"), and associate it with your VPC.

Add Routes:

   * If you want a public subnet to access the internet, you’ll need to add a route that points to an Internet Gateway (more on that in the next step).

**STEP 5:** Attach an Internet Gateway (For Public Subnets)

If you want to allow instances in your public subnets to access the internet, you need to create and attach an Internet Gateway (IGW).

   1. In the VPC Dashboard, click Internet Gateways in the left sidebar.
   2. Click Create Internet Gateway and give it a name.
   3. Once created, click Attach to VPC and select the VPC you created earlier.
