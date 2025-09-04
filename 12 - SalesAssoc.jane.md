
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

This IAM policy grants `SalesAssoc.jane` access to key AWS services for monitoring, storage, and analytics. It includes permissions for Amazon QuickSight, S3, SNS, CloudWatch metrics and logs

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

<img src="https://i.imgur.com/Z1WKpYF.jpeg" height="100%" width="100%" /> 


| **CloudWatch Feature**   | **Access Outcome**                                                   | **Permissions Likely Present**                       | **Permissions Missing**                                                                         |
| ------------------------ | -------------------------------------------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Alarms**               |  Cannot view alarms (error shown)                                   | None for alarms                                      | `cloudwatch:DescribeAlarms`, `cloudwatch:ListAlarms`, `cloudwatch:GetAlarm*`                    |
| **Logs (Logs Insights)** | Can access Logs Insights interface, see discovered fields          | `logs:DescribeLogGroups`, `logs:DescribeLogStreams`  | Possibly `logs:GetLogEvents`, `logs:FilterLogEvents`, `logs:StartQuery`, `logs:GetQueryResults` |
| **Metrics**              |  Can access Metrics page, see namespaces (Logs, Usage), run queries | `cloudwatch:ListMetrics`, `cloudwatch:GetMetricData` | Possibly `cloudwatch:GetMetricStatistics`                                                       |





##  **Summary**:
   **SalesAssoc.jane has **partial read access**.
   
   **Allowed:** Logs interface + Metrics panel.
   
   **Denied:** Alarms (completely blocked).



1. **IAM Group Membership**

   * `SalesAssoc.jane` is part of the **ProjectX-Team** AWS group.
   * The group policy likely grants **limited monitoring permissions** (logs and metrics) for team members but does not include **alarms access**.
   * This design is common: CloudWatch alarms are often restricted to DevOps, CloudOps, or Security teams because alarms control **critical system monitoring**.


2. **Role as a Sales Associate**

   * A sales associate generally doesn’t need full CloudWatch visibility.
   * They might require **metrics dashboards** (usage, performance KPIs, cost-related metrics) or **logs insights** (if tied to sales analytics), but **alarms** are operational alerts for system health (CPU usage spikes, failed deployments, etc.) — usually irrelevant to sales.
   * So, permissions were likely scoped intentionally:

     * **Allowed:** Logs + Metrics (useful for business reporting, sales dashboards, or application usage tied to sales data).
     * **Denied:** Alarms (to avoid unnecessary exposure to infrastructure-level alerts).


3. **Policy Design Principle: Least Privilege**

   * AWS recommends giving users **only what they need**.
   * Since `SalesAssoc.jane` is not part of the operations or security team, **alarm visibility was excluded**.
   * This explains the error message in CloudWatch when she tried to access alarms.


##  ** **Conclusion:****

The partial access is **intentional**. As a **Sales Associate** in the **ProjectX-Team**, Jane only needs **visibility into metrics and logs** relevant to business performance — **not operational alarms**.




