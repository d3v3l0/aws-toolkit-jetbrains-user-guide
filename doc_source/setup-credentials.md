# Setting AWS Credentials for the AWS Toolkit for JetBrains<a name="setup-credentials"></a>

To access an AWS account with the AWS Toolkit for JetBrains, you must first connect the AWS Toolkit to that account\. You do this by specifying which AWS credentials for that account that the AWS Toolkit will use to make that connection\.

Complete the following procedures to make an initial connection, switch between connections, change connections, delete connections, and more\.

**Topics**
+ [Connecting for the First Time](#setup-credentials-first-connect)
+ [Getting the Current Connection](#setup-credentials-current-connect)
+ [Adding Multiple Connections](#setup-credentials-multiple-connect)
+ [Switching Between Connections](#setup-credentials-switch-connect)
+ [Changing Connection Settings](#setup-credentials-change-connect)
+ [Deleting a Connection](#setup-credentials-delete-connect)

## Connecting for the First Time<a name="setup-credentials-first-connect"></a>

Assuming that you have already [installed the AWS Toolkit](key-tasks.md#key-tasks-install), then to complete this procedure, you must first have an [access key](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) \(which contains both an *access key ID* value and a *secret access key* value\) for a user in IAM \(which we recommend\) or AWS account root user \(which we strongly discourage\)\. \(If you don't have an access key for a user in IAM already, [create one](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_CreateAccessKey)\.\)

1. With your access key ID value and secret access key value ready, do one of the following\.
   + On the status bar, choose **AWS: No credentials selected**, and then choose **Edit AWS Credential file\(s\)**\.  
![\[AWS no credentials selected on the status bar\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)  
![\[Edit AWS credentials from the status bar\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)
   + [Open the AWS Explorer](key-tasks.md#key-tasks-open-explorer), if it is not already open\. Choose **Configure AWS Connection**, and then choose **Edit AWS Credential file\(s\)**\.  
![\[Configure AWS connection from the AWS Explorer\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)  
![\[Edit AWS credentials from the AWS Explorer\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)

1. In the file, next to `[default]`, for `aws_access_key_id`, replace `[accessKey1]` with your access key ID value \(for example, `AKIAIOSFODNN7EXAMPLE`\)\.

   If prompted, select **I want to edit this file anyway**, and then choose **OK**\.

1. For `aws_secret_access_key`, replace `[secretKey1]` with your secret access key value \(for example, `wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY`\)\.

   The final results should look as follows, following the [named profile](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html) format\.

   ```
   ... Other file contents omitted for brevity ...
   
   [default]
   # ... Some comments ...
   aws_access_key_id = AKIAIOSFODNN7EXAMPLE
   # ... Some more comments ...
   # ... Some more comments ...
   # ... Some more comments ...
   # ... Some more comments ...
   aws_secret_access_key = wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
   
   ... Other file contents omitted for brevity ...
   ```
**Note**  
The AWS Toolkit currently supports the following configuration variables\.  
`aws_access_key_id`
`aws_secret_access_key`
`aws_session_token`
`credential_process`
`mfa_serial`
`role_arn`
`source_profile`
For more information, see [AWS CLI Configuration Variables](https://docs.aws.amazon.com/cli/latest/topic/config-vars.html) in the *AWS CLI Command Reference*\.

1. Save and then close the file\. The AWS Toolkit attempts to connect to the account by using the preceding access key\. After connecting, you can use the AWS Toolkit to work with AWS resources in that account such as [AWS serverless](key-tasks.md#key-tasks-sam) applications, [AWS Lambda](key-tasks.md#key-tasks-lambda) functions, and [AWS CloudFormation](key-tasks.md#key-tasks-cloudformation) stacks\.

You can also have [more than one connection](key-tasks.md#key-tasks-multiple-connect) available, so that you can [switch between them](key-tasks.md#key-tasks-switch-connect), if you want\.

After you connect, the AWS Toolkit selects the default AWS Region automatically\. You might need to [switch to working with AWS resources in that account that are in a different Region](key-tasks.md#key-tasks-switch-region)\.

## Getting the Current Connection<a name="setup-credentials-current-connect"></a>

To check which connection the AWS Toolkit is currently using, do one of the following\.
+ On the status bar, the current connection is displayed in the **AWS Connection Settings** area\.  
![\[The current connection in the status bar\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)
+ [Open the AWS Explorer](key-tasks.md#key-tasks-open-explorer), if it is not already open, and then choose **Show Options Menu** \(the gear icon\)\. Choose **AWS Connection Settings**\. The current connection is selected\.  
![\[The current connections in the AWS Explorer\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)

You can also have [more than one connection](key-tasks.md#key-tasks-multiple-connect) available, so that you can [switch between them](key-tasks.md#key-tasks-switch-connect), if you want\.

## Adding Multiple Connections<a name="setup-credentials-multiple-connect"></a>

To complete this procedure, you must first have the additional [access key](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) \(which contains both an *access key ID* value and a *secret access key* value\) for a user in IAM \(which we recommend\) or AWS account root user \(which we strongly discourage\)\. \(If you don't have an access key for a user IAM already, [create one](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_CreateAccessKey)\.\)

1. [Connect for the first time](key-tasks.md#key-tasks-first-connect), if you have not done so already\.

1. With the additional access key ID value and secret access key value ready, do one of the following\.
   + On the status bar, choose **AWS Connection Settings**, and then choose **All Credentials, Edit AWS Credential file\(s\)**\.  
![\[Choosing to edit AWS credentials from the status bar\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)
   + [Open the AWS Explorer](key-tasks.md#key-tasks-open-explorer), if it is not already open, and then choose **Show Options Menu** \(the gear icon\)\. Choose **AWS Connection Settings, All Credentials, Edit AWS Credential file\(s\)**\.  
![\[Choosing to edit AWS credentials from the AWS Explorer\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)

1. In the file, add a [named profile](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html) for each additional connection\. Profile names can contain only the letters `A` through `Z`, the letters `a` through `z`, the numbers `0` through `9`, the hyphen character \(`-`\), and the underscore character \(`_`\)\. Profile names must be less than 64 characters in length\. 

   For example, for a named profile named `myuser`, use the following format\.

   ```
   [profile myuser]
   aws_access_key_id = AKIAIOSFODNN7EXAMPLE
   aws_secret_access_key = wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
   ```
**Note**  
The AWS Toolkit currently supports named profiles with only the following characters: `A`\-`Z`, `a`\-`z`, `0`\-`9`, underscore \(`_`\), and dash \(`-`\)\.  
The AWS Toolkit also currently supports only the following configuration variables\.  
`aws_access_key_id`
`aws_secret_access_key`
`aws_session_token`
`credential_process`
`mfa_serial`
`role_arn`
`source_profile`
For more information, see [AWS CLI Configuration Variables](https://docs.aws.amazon.com/cli/latest/topic/config-vars.html) in the *AWS CLI Command Reference*\.

1. Save and then close the file\. The AWS Toolkit displays the new connection in the **AWS Connection Settings** menu in both the status bar and in the **AWS Explorer**\.

Now that you have multiple connections, you can [switch between them](key-tasks.md#key-tasks-switch-connect), if you want\.

After you connect, you might need to [switch to working with AWS resources in that account that are in a different AWS Region](key-tasks.md#key-tasks-switch-region)\.

## Switching Between Connections<a name="setup-credentials-switch-connect"></a>

1. [Add multiple connections](key-tasks.md#key-tasks-multiple-connect), if you have not done so already\.

1. Do one of the following:
   + On the status bar, choose **AWS Connection Settings**\.
   + [Open the AWS Explorer](key-tasks.md#key-tasks-open-explorer), if it is not already open, and then choose **AWS Connection Settings**\.

1. Choose the name of the [named profile](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html) that you want to use for the new connection\. If it is not listed, first choose **All Credentials**, and then choose the name of the named profile that you want to use\.   
![\[Switching the current connection\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)

   The AWS Toolkit switches to using the new connection, which is now selected in the **AWS Connection Settings** menu in both the status bar and the **AWS Explorer**\.

After you connect, you might need to [switch to working with AWS resources in that account that are in a different AWS Region](key-tasks.md#key-tasks-switch-region)\.

## Changing Connection Settings<a name="setup-credentials-change-connect"></a>

1. Do one of the following:
   + On the status bar, choose **AWS Connection Settings, All Credentials, Edit AWS Credentials file\(s\)**\.  
![\[Choosing the Edit Credential files command\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)
   + [Open the AWS Explorer](key-tasks.md#key-tasks-open-explorer), if it is not already open, and then choose **Show Options Menu** \(the gear icon\)\. Then choose **AWS Connection Settings, All Credentials, Edit AWS Credential file\(s\)**\.  
![\[Choosing the Edit Credential files command\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)

1. Make your changes to the file, and then save and close the file\. 

## Deleting a Connection<a name="setup-credentials-delete-connect"></a>

1. Do one of the following:
   + On the status bar, choose **AWS Connection Settings, All Credentials, Edit AWS Credentials file\(s\)**\.  
![\[Choosing the Edit Credential files command\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)
   + [Open the AWS Explorer](key-tasks.md#key-tasks-open-explorer), if it is not already open, and then choose **Show Options Menu** \(the gear icon\)\. Then choose **AWS Connection Settings, All Credentials, Edit AWS Credential file\(s\)**\.  
![\[Choosing the Edit Credential files command\]](http://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/)

1. In the file, completely delete the [named profile](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html) \(including the named profile's name, access key ID, and secret access key\) for the connection that you want to delete\.

1. Save and then close the file\. The AWS Toolkit removes the deleted connection from the **AWS Connection Settings** menu in both the status bar and in the **AWS Explorer**\.

After you delete a connection, you might need to [switch to a different connection](key-tasks.md#key-tasks-switch-connect) or [connect for the first time](key-tasks.md#key-tasks-first-connect) again\.