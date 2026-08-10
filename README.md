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
<img width="1919" height="869" alt="image" src="https://github.com/user-attachments/assets/5f38a561-1d1f-4ffa-bb04-5174ae0f2702" />

---

### Step 2: Explore IAM Groups and Policies

Open **IAM → User groups** and verify:

| Group | Policy |
|---|---|
| `EC2-Admin` | Inline Policy |
| `EC2-Support` | `AmazonEC2ReadOnlyAccess` |
| `S3-Support` | `AmazonS3ReadOnlyAccess` |

#### Output

<img width="1919" height="883" alt="image" src="https://github.com/user-attachments/assets/feceedc1-587c-425a-b487-68121aaa7365" />


---

### Step 3: Assign Users to Groups

Assign users according to the following business scenario:

| User | Group | Permission |
|---|---|---|
| `user-1` | `S3-Support` | Read-only S3 access |
| `user-2` | `EC2-Support` | Read-only EC2 access |
| `user-3` | `EC2-Admin` | View, Start and Stop EC2 |

#### Output
<img width="1919" height="883" alt="image" src="https://github.com/user-attachments/assets/e22633ee-37b2-4247-b9c0-4b20fcf5aa55" />
<img width="1919" height="864" alt="image" src="https://github.com/user-attachments/assets/3b70f935-4681-4cc3-a597-b732a2fb77c1" />
<img width="1919" height="882" alt="image" src="https://github.com/user-attachments/assets/f3676f87-697d-41a6-8247-dd31d0ff9b7a" />


---

### Step 4: Test user-1 — S3 Support

Sign in using:
Open **Amazon S3** and verify that the user can view the available bucket and its contents.

Then open **Amazon EC2** and verify that access is denied.

#### Output
<img width="1917" height="861" alt="image" src="https://github.com/user-attachments/assets/eb773ad7-ae3d-4094-b0a3-68e8349fae15" />
<img width="1919" height="1024" alt="image" src="https://github.com/user-attachments/assets/8f16aa4e-b963-419e-890b-67b2eb474701" />

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
<img width="1919" height="1031" alt="image" src="https://github.com/user-attachments/assets/83237700-84f3-448e-90af-c3046ad4a071" />

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
<img width="1919" height="868" alt="image" src="https://github.com/user-attachments/assets/5d8cd628-6d5b-4fdd-bb11-6b5f0704a780" />
<img width="1032" height="364" alt="image" src="https://github.com/user-attachments/assets/e5b33685-0a54-4a1a-a5ef-fab2a5518ec2" />
<img width="1919" height="865" alt="image" src="https://github.com/user-attachments/assets/36c4b0a8-c433-46cb-9e3a-6414bbef655f" />


## OUTPUT
IAM users are successfully assigned to groups with appropriate permissions.
```
user-1 → S3-Support → S3 Read-Only
user-2 → EC2-Support → EC2 Read-Only
user-3 → EC2-Admin → EC2 View/Start/Stop
```
The permission restrictions are successfully verified by testing access to Amazon S3 and Amazon EC2.
<img width="1919" height="872" alt="image" src="https://github.com/user-attachments/assets/d0b343ca-fa78-497e-8a15-9fc01b24fdc7" />
<img width="1919" height="873" alt="image" src="https://github.com/user-attachments/assets/912caaaf-5e05-4519-8d6c-b3728f2697b2" />


## RESULT

Thus, AWS IAM users, groups, and policies were successfully explored and configured. Users were assigned appropriate role-based permissions, and their access to Amazon S3 and Amazon EC2 was successfully tested and verified.
