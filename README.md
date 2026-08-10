# T1-26-27 EX 6 — IAM
## REG NUMBER: 212223220036
## NAME: INESH N

## AIM

To explore AWS Identity and Access Management (IAM), inspect users, groups and policies, assign users to appropriate groups, and test their permissions on AWS services.

## ALGORITHM

1. Open the AWS Management Console and select **IAM**.
2. Explore the pre-created IAM users and groups.
3. Inspect the policies attached to the groups.
4. Add users to groups according to their roles.
5. Obtain the IAM users sign-in URL.
6. Sign in as different IAM users.
7. Test their permissions on Amazon S3 and Amazon EC2.
8. Verify that each user can perform only the actions allowed by their assigned policy.

## PROCEDURE

### Step 1: Explore IAM Users

Open **IAM → Users** and verify the following users:

- `user-1`
- `user-2`
- `user-3`

Select `user-1` and inspect the **Permissions**, **Groups**, and **Security credentials** tabs.

#### Output

> Paste the screenshot of IAM Users here.

---

### Step 2: Explore IAM Groups and Policies

Open **IAM → User groups** and verify:

| Group | Policy |
|---|---|
| `EC2-Admin` | Inline Policy |
| `EC2-Support` | `AmazonEC2ReadOnlyAccess` |
| `S3-Support` | `AmazonS3ReadOnlyAccess` |

#### Output

> Paste the screenshot showing IAM groups and policies here.

---

### Step 3: Assign Users to Groups

Assign users according to the following business scenario:

| User | Group | Permission |
|---|---|---|
| `user-1` | `S3-Support` | Read-only S3 access |
| `user-2` | `EC2-Support` | Read-only EC2 access |
| `user-3` | `EC2-Admin` | View, Start and Stop EC2 |

#### Output

> Paste the screenshot showing users assigned to their groups here.

---

### Step 4: Test user-1 — S3 Support

Sign in using:
Open **Amazon S3** and verify that the user can view the available bucket and its contents.

Then open **Amazon EC2** and verify that access is denied.

#### Output

> Paste the screenshots showing S3 access and EC2 access denied here.

---

### Step 5: Test user-2 — EC2 Support

Sign in using:

```text
Username : user-2
Password : Lab-Password2
```
Open **Amazon EC2** and verify that the user can view EC2 instances.

Attempt to stop the `LabHost` instance. The operation should be denied because the user has read-only permissions.

Open **Amazon S3** and verify that bucket access is denied.

### Output



---

### Step 6: Test user-3 — EC2 Admin

Sign in using:

```text
Username : user-3
Password : Lab-Password3

```text
Username : user-1
Password : Lab-Password1

Open Amazon EC2 and select the LabHost instance.

Choose Instance state → Stop instance and confirm the operation.

The instance should successfully enter the stopping state.
```
### Output

## OUTPUT
IAM users are successfully assigned to groups with appropriate permissions.

user-1 → S3-Support → S3 Read-Only
user-2 → EC2-Support → EC2 Read-Only
user-3 → EC2-Admin → EC2 View/Start/Stop

The permission restrictions are successfully verified by testing access to Amazon S3 and Amazon EC2.


## RESULT

Thus, AWS IAM users, groups, and policies were successfully explored and configured. Users were assigned appropriate role-based permissions, and their access to Amazon S3 and Amazon EC2 was successfully tested and verified.
