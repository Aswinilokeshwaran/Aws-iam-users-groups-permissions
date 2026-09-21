# IAM Users, Groups and Permissions on AWS

Created an IAM group and user with read-only EC2 access, then tested that the permissions work.

## Services used
- AWS IAM (users, groups, managed policies)
- Amazon EC2 (used to test the permissions)

## What I did
- Created an IAM user group called support-readonly
- Attached the AWS managed policy AmazonEC2ReadOnlyAccess to the group
- Created an IAM user called achu-support-user with console access
- Added the user to the support-readonly group (not to an admin group)
- Signed in as the new user in a private browser window
- Confirmed the user can view the EC2 Instances page
- Tried to launch an EC2 instance and got a "not authorized" error, which shows the read-only permission works
- Deleted the test user and group after testing

## Screenshots

### User group with read-only policy
![IAM group](screenshots/1-iam-group.jpeg)

### Test user created
![IAM user](screenshots/2-iam-user.jpeg)

### Launch blocked (not authorized)
![Access denied](screenshots/3-access-denied.jpeg)

## What I learned
- Permissions are best given to groups, not directly to users
- Least privilege means giving users only the access they need
- AWS managed policies like AmazonEC2ReadOnlyAccess save time
- An "AccessDenied" or "not authorized" error means the policy is doing its job
