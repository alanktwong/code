
# Identity and Access Management

[Identity and Access Mangement](https://aws.amazon.com/iam/)

## Principal/Identity

* An [identity](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html) is a person or service with permissions to do stuff in AWS. These are:
  * Users
  * User Groups
  * Roles
  * AKA Principal
* An [user](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html) will have:
  * Username
  * Password
  * Up to 2 access keys
    * AKs are used by APIs and/or CLI
* Use user accounts when the person/service needs permanent rights.

## User Group

* Users/identities can belong to a [user group](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html)
* Permissions should be managed at the group level
* Group membership can be controlled

## Role

* A [role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html) is an identity that is temporarily granted permissions.
* They aren't permanent assignments.
* Assumable by any entity with a need for it.
* Good reasons to think even user accounts should always work within roles.
* Compatible with federated identity
  * Concept of federated identity is to connect users that exist in one IdM system and granting them permissions to take actions in another system.
  * Simpler term often used is SSO
* Use roles for applications

## AWS Root User

* The [root user](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html) is the email address/password that created the AWS Account
  * Store in encrypted vault obviously
* They have rights to everything in that account - god mode 
  * Changing the billing plan
  * Create Cloudfront Key pair
  * enable MFA for S3 bucket
  * restore permissions for other users
* Do *not* use for everyday access.
* Create & use other admin accounts

## Authentication

* Validation of credentials to provide identity within a system
  * Challenge what the prospective user knows (password or screen)
  * Challenge what the prospective user has (e.g. thumbprint or retinal scan or weight -> "human trap")
* Single factor authentication only challenges once
* Multi factor authentication only challenges more than once
* For GUI, authenticate with username/password
* For CLI/Apps, authenticate with access keys and secret keys.

## Authorization: Policies & Permissions

[AWS Access Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

* Expressed in JSON
  * Not required to know for exam, but good to be able to read
* Validates actions that principals take
* Identity-based policies
  * Can link to a user, group or role.
  * Best to link to a group or role
* Resource-based policies
  * Linked to a resource
  * usually for cross-account access
* By default all actions are denied
* Explicit Allows overrides defaults
* Permission Boundaries can override Explicit Allows
* Explicit Denies overried Explicit Allows -> i.e. Explicit Denies always wins
* AWS IAM Policies
  * action
  * resources
  * conditions
* OOTB Examples from AWS: `AdministratorAccess`, `AmazonS3FullAccess`, `AmazonS3ReadOnlyAccess`, etc.

E.g. AdministratorAccess json =>
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}
```

## Multi-Factor authentication

[AWS MFA Features](https://aws.amazon.com/iam/features/mfa/)

MFA Form Factors could be:
* Virtual MFA devices - any smartphone or tablet that supports the [time-based one-time password (TOTP)](https://en.wikipedia.org/wiki/Time-based_One-Time_Password) standard
* SMS 

Remember multi-factor authentication (MFA) means that we challenge the login user's identity more than once.
It is best practice to use it.

A factor may be:
* Something the user knows
  * E.g. password, security Q&A, PIN, etc.
* Something the user has
  * E.g. a physical device FOB that emits a rotating code
* Something the user is
  * E.g. biometrics (e.g. fingerprint, retinal scan)
* Something the user receives
  * E.g. a OTP texted/emailed to the user



[AWS MFA User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html)

## Key Rotation

Access keys are used to access AWS programmatically
(e.g. via the [AWS CLI](https://aws.amazon.com/cli/)
or AWS SDK in [Python](https://aws.amazon.com/sdk-for-python/),
[JavaScript](https://aws.amazon.com/sdk-for-javascript/),
[Java](https://aws.amazon.com/sdk-for-java/),
[Ruby](https://aws.amazon.com/sdk-for-ruby/),
[Go Lang](https://aws.amazon.com/sdk-for-go/,
[PHP](https://aws.amazon.com/sdk-for-php/),
[.NET](https://aws.amazon.com/sdk-for-net/),
[C++](https://aws.amazon.com/sdk-for-cpp/), etc.)

Best practice is to rotate these keys periodically.

Not every account needs these keys. E.g. a user who only will work on AWS via the AWS Web Console

Key Rotation Process

1. Create a 2nd access key in addition to the one in use
2. Update all your applications to use the new access key
3. Validate the applications are still working.
4. Change state of previous access key inactive.
5. Validate the applications are still working (b/c you may have missed one in step 3)
6. Only if (5) passes for all apps, you should delete the previous access key.
   If it fails for some apps, reactivate the previous key and switch over to the new access key.


E.g. check your access key: `aws iam list-access-keys --user-name alan.wong`

```json
{
    "AccessKeyMetadata": [
        {
            "UserName": "alan.wong",
            "AccessKeyId": "alphanumeric(20)",
            "Status": "Active",
            "CreateDate": "2021-05-04T17:14:55+00:00"
        }
    ]
}
```

If you create an access key, you will get back the secret and the AccessKeyId

E.g. check your access key: `aws iam create-access-key --user-name alan.wong`

```json
{
    "AccessKeyMetadata": [
        {
            "UserName": "alan.wong",
            "AccessKeyId": "alphanumeric(20)",
            "SecretAccessKey": "alphanumeric(40)",
            "Status": "Active",
            "CreateDate": "2021-05-04T17:14:55+00:00"
        }
    ]
}
```

## Multi permissions

## AWS compliance program

## AWS responsiblity model

## Shared responsibility model

## Best practices: user accounts

## Best practices: password policies

## Best practices: credential rotation

## Best practices: principle of least privilege

## Best practices: IAM Role

## Best practices: Policy Conditions
