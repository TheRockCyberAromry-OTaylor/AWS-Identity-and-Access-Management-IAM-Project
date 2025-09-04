
<img src="https://i.imgur.com/jJPHPKY.jpeg" height="100%" width="100%" /> 


## CloudAdmin_Tuss logged-in


1. **User Selection**
   
   * From the left navigation panel in the IAM service, the **administrator went** to **Access management → Users**.
   * They selected the IAM user **`SalesAssoc.jane`**.
   * This is confirmed by the navigation Path indicator at the top (`IAM > Users > SalesAssoc.jane`) with the red arrow pointing at the username.


2. **Viewing User Details**

   * In the **Summary** panel for `SalesAssoc.jane`, the following details were visible:

     * **ARN** (Amazon Resource Name) of the user.
     * **Created date**: July 18, 2025.
     * **Last console sign-in**: Today ( green check).
     * **Access key**: None created yet (option available to create one).


3. **Navigating to Permissions**

   * The administrator clicked on the **Permissions** tab (highlighted in blue).
   * This shows what policies are currently attached to this user.


4. **Inspecting Attached Policy**

   * In the **Permissions policies** section:

     * A custom **inline policy** named **`Perms@SalesAssoc`** 
     * Type: `Customer inline` → meaning this policy is created specifically for this user (not a reusable managed policy).
     * Attached via: **Inline**.Inline policies are written in JSON (the IAM policy language).



5. **Copy of the  written JSON policy **`Perms@SalesAssoc`** attached** to  `SalesAssoc.jane`

   
##  IAM Policy: `Perms@SalesAssoc` for `SalesAssoc.jane`

This IAM policy grants `SalesAssoc.jane` access to key AWS services for monitoring, storage, and analytics. It includes permissions for Amazon QuickSight, S3, SNS, CloudWatch metrics

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "QuickSightAccess",
      "Effect": "Allow",
      "Action": "quicksight:DescribeAccountSubscription",
      "Resource": "*"
    },
    {
      "Sid": "S3Access",
      "Effect": "Allow",
      "Action": [
        "s3:ListAllMyBuckets",
        "s3:CreateBucket",
        "s3:ListBucket"
      ],
      "Resource": "*"
    },
    {
      "Sid": "SNSListAccess",
      "Effect": "Allow",
      "Action": [
        "sns:ListPlatformApplications",
        "sns:ListTopics",
        "sns:ListSubscriptions"
      ],
      "Resource": "*"
    },
    {
      "Sid": "CloudWatchMetricsAccess",
      "Effect": "Allow",
      "Action": "cloudwatch:ListMetrics",
      "Resource": "*"
    },
    {
      "Sid": "LogsAccess",
      "Effect": "Allow",
      "Action": "logs:DescribeLogGroups",
      "Resource": "*"
    }
  ]
}
```

---


