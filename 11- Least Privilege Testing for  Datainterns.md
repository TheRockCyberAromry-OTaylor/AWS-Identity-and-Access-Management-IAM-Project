
<img src="https://i.imgur.com/tqkcB0u.png" height="100%" width="100%" /> 



1. **User `Data-Interns@Hawa.Tombo`  logged in and Navigated to Amazon S3 Console**
   - Opened the AWS Management Console and selected **Amazon S3** from the services menu.
     

2. **Selected “General purpose buckets” Tab**
   - Within the S3 dashboard,clicked on the **“General purpose buckets”** tab to view existing buckets.

3. **Triggered Access Denied Error**
   - Upon accessing this tab, an **“Access Denied”** error appeared in a red box.
   - This suggests the IAM role or user currently signed in lacks the necessary **S3 ListBucket** or **Read** permissions for the buckets in that region.

4. **Prompted to Diagnose with Amazon Q**
   - AWS surfaced a **“Diagnose with Amazon Q”** button, offering automated troubleshooting via their AI assistant.


### Possible Causes of the Error

- **IAM Policy Restrictions**: The signed-in user `Data-Interns@Hawa.Tombo` might not have `s3:ListBucket` or `s3:GetBucketLocation` permissions.
- **Bucket-Level Permissions**: The bucket may have a restrictive bucket policy or ACL that blocks access.
- **Bucket Policy Denial**  The bucket policy may contain a `Deny` statement or fail to include an `Allow` for the requesting principal
- **Cross-Account Access**: If the bucket belongs to another AWS account, proper trust relationships or resource policies may be missing.
- **Service Control Policies (SCPs)**: If using AWS Organizations, SCPs might be limiting access.


## `Data-Interns@Hawa.Tombo` Assume the role  Role@DataInterns001 @ 3743******** to view existing buckets

 <img src="https://i.imgur.com/KHtenp4.jpeg" height="100%" width="100%" />  

 User logged in with Role@DataInterns001 in AWS account 3743********.

- Opened the Amazon S3 service.

- Navigated to General Purpose Buckets view.

- Viewed the list of buckets → only one bucket (olatunji28bucket) is present in us-east-1.

- Console shows extra insights (Storage Lens, External Access Summary) for visibility into usage and security.


## **Scenario 1: IAM User `Data-Interns@Hawa.Tombo`**

* **Login Identity:** Direct IAM **user account**.
* **Access Behavior:**

  * When logging in directly, the user only has **permissions explicitly attached** to their IAM user (or inherited via groups).
  * In the earlier screenshot, the user could not list S3 buckets → means **their user account has no S3-related permissions** (missing `s3:ListAllMyBuckets` or `s3:ListBucket`).
* **Result:** Access Denied when attempting to view S3 buckets.
* **Priority Level:** **Low** — restricted intern-level access, least privilege enforced.


## **Scenario 2: IAM Role `Role@DataInterns001` (with `Policy@DataInterns001` attached)**

* **Login Identity:** IAM **role** assumed by the user.
* **Policy Attached:** `Policy@DataInterns001` is explicitly attached to this role.
* **Access Behavior:**

  * The permissions granted are controlled by `Policy@DataInterns001`.
  * Since the role successfully listed and displayed the bucket `olatunji28bucket`, we know the policy **includes at least read-only S3 permissions** like:

    * `s3:ListAllMyBuckets`
    * `s3:ListBucket`
* **Result:** User (through the role) can successfully view and access bucket metadata.
* **Priority Level:** **Medium/High** — elevated temporary access granted by the role + policy attachment.


## **Comparison: IAM User vs. IAM Role (with Policy\@DataInterns001)**

| Aspect               | IAM User (`Data-Interns@Hawa.Tombo`) | IAM Role (`Role@DataInterns001` + `Policy@DataInterns001`) |
| -------------------- | ------------------------------------ | ---------------------------------------------------------- |
| **Login Type**       | Direct IAM user login                | Assumed IAM role with policy attached                      |
| **Policy Attached**  | No S3 policy attached                | `Policy@DataInterns001` attached to role                   |
| **Access Outcome**   | Access Denied (cannot list buckets)  | Allowed (can list and view buckets)                        |
| **Permission Scope** | Very limited, no S3 actions granted  | Includes S3 read/list actions (defined in policy)          |
| **Use Case**         | Everyday restricted intern access    | Temporary elevated access for specific intern tasks        |
| **Priority Level**   | Low                                  | Higher (depends on what’s in the policy)                   |


 **Summary:**

* The **IAM user** has **no S3 permissions** by default, keeping their access minimal.
* The **IAM role** (`Role@DataInterns001`) inherits the permissions from **`Policy@DataInterns001`**, giving them the ability to **list and view buckets**.
* This setup enforces **separation of duties**: the user identity is locked down, but the role + attached policy allows interns to perform specific approved tasks.














 
 <img src="https://i.imgur.com/DPBgcOX.jpeg" height="100%" width="100%" /> 

- User logged in as Data-Interns@Hawa.Tombo.

- Navigated to AWS DMS → Enhanced Monitoring.

- Console attempted to fetch replication tasks, endpoints, and alarms.

- User lacked required IAM permissions (dms:DescribeReplicationTasks, cloudwatch:DescribeAlarms), causing failures.

- Dashboard displayed zero resources and error messages instead of monitoring data.
 
 ### Possible Causes of the Error

 The **possible cause of the error** is that the IAM user **`Data-Interns@Hawa.Tombo`** does not have the necessary **permissions** in their IAM policy.

Specifically:

* Missing **`dms:DescribeReplicationTasks`** : prevents DMS from showing replication tasks and endpoints.
* Missing **`cloudwatch:DescribeAlarms`** : prevents CloudWatch alarms from being retrieved.

 In short: The error happens because the user’s IAM policy is too restrictive and does not include the required **read-only permissions** for **DMS** and **CloudWatch monitoring**.


 
    
 <img src="https://i.imgur.com/wi2F4xg.jpeg" height="100%" width="100%" />                                                                       
 
- User Data-Interns@Hawa.Tombo opened the CloudWatch service.

-  Data-Interns@Hawa.Tombo attempted to fetch alarms using cloudwatch:DescribeAlarms.

- The IAM user lacked that permission, so the request was denied.

- Dashboard showed a red error banner and no alarm data.
 
 ### Possible Causes of the Error

- Missing cloudwatch:DescribeAlarms in the user’s IAM policy.

- Policy or Service Control Policy (SCP) explicitly denying CloudWatch.

- User logged in directly instead of assuming a role with proper permissions.

- Region mismatch (alarms exist in another AWS region).

- Most likely: The IAM user lacks the cloudwatch:DescribeAlarms permission.
 

## `Data-Interns@Hawa.Tombo` Assume the role  Role@DataInterns001 @ 3743******** to view existing buckets

 <img src="https://i.imgur.com/KHtenp4.jpeg" height="100%" width="100%" />  

 User logged in with Role@DataInterns001 in AWS account 3743********.

- Opened the Amazon S3 service.

- Navigated to General Purpose Buckets view.

- Viewed the list of buckets → only one bucket (olatunji28bucket) is present in us-east-1.

- Console shows extra insights (Storage Lens, External Access Summary) for visibility into usage and security.
