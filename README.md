# NextWork.org Cloud Security with AWS IAM

## Project Documentation

### Introduction
This project focuses on using AWS Identity and Access Management (IAM) to enhance cloud security by managing permissions for users, groups, and roles within an AWS account.

### What is AWS IAM?
AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources by enabling you to manage permissions for users, groups, and roles within your AWS account.

### How I'm Using AWS IAM in This Project
In today's project, I used AWS IAM to create and manage user groups and attach policies to these groups, ensuring that all users within each group had the appropriate permissions to access and perform specific actions.

### One Thing I Didn't Expect
One thing I didn't expect in this project was the complexity of fine-tuning IAM policies to ensure the principle of least privilege, which required meticulous testing.

### Project Duration
This project took me 30 minutes.

### Tags
Tags are tools to categorize your collections and instances. The tag I’ve used on my EC2 instances is called `environments`. The values I’ve assigned for my instances are `development` and `production`.

### IAM Policies
IAM Policies are policies that allow you to configure identity access. For this project, I’ve set up a policy using JSON code. I’ve created a policy that allows people with development credentials to access EC2 instances.

When creating a JSON policy, you have to define its **Effect**, **Action**, and **Resource**. The **Effect**, **Action**, and **Resource** attributes in a JSON policy define whether access is allowed or denied, specify the actions that can be performed, and identify the resources those actions apply to, respectively.

### My JSON Policy

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:StopInstances",
      "Resource": "arn:aws:ec2:region:account-id:instance/instance-id"
    }
  ]
}

### Account Alias
An account alias is an easily recognized name or label representing a general ledger account number, which can be used instead of the account number during transactions to simplify identification and management. Creating an account alias took me 2 minutes. Now, my new AWS console sign-in URL is `nextwork-alias-vincent`.

### IAM Users and User Groups
**Users**: IAM users are entities within AWS Identity and Access Management (IAM) that represent individual people or applications, allowing them to authenticate and make requests to AWS services, with permissions defined by policies attached to them.

**User Groups**: IAM user groups are collections of IAM users managed as a unit, allowing administrators to attach identity-based policies to the group so that all users within the group receive the same permissions. Attaching the policy you created to a user group means that all IAM users within that group inherit the permissions defined in the policy.

### Logging in as an IAM User
The first way is to email the instructions. Once I logged in as my IAM user, I noticed some access denied sections.

### Testing IAM Policies
I tested my JSON IAM policy by stopping the production instance and the development instance.

**Stopping the production instance**: When I tried to stop the production instance, I got an error because I was not authorized to change anything.

**Stopping the development instance**: Next, when I tried to stop the development instance, it ran because this user has access to the developers instance.

---

Everyone should be in a job they love.

Vincent Mostert
```
