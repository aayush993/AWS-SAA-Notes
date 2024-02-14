When Only Account ID is shown. It means it’s a root user. And, It is not recommended to use root user. That is why we will use users which will allow us use our account securely. 

Firstly we will be creating admin users.
User Type:
       Instead of specifying user with identity center.
       We will create an IAM user. This is required with exam perspective.

Password:
       If you are creating a user for someone else, then select auto generate password and select user must change password on sign in.

Permissions:
       Add it directly or attach the user to a group.
       Let’s create a group called admin

Now, In IAM dashboard. In AWS Account set your Account alias. This account alias can be used in lieu of your account ID. When logging in to a admin user or any other user of the organization. 

Or the account url can be shared within the organization to directly jump to the sign-in page for the organization’s account user. 

Make sure, admin and root users are safe as loosing them will cause you to contact customer support.