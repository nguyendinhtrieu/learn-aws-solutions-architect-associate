- `Version`: specifies the language syntax rules that are to be used to process a policy.
- `Id` (Optional): specifies an optional identifier for the policy.
- `Statements` (Required): is the main element for a policy. This element is required. The Statement element can contain a single statement or an array of individual statements. Each individual statement block must be enclosed in curly braces { }. For multiple statements, the array must be enclosed in square brackets [ ].
  - `Sid` (Optional): Statement ID
  - `Effect`: Allow/Deny
  - `Principal`: Specify the principal that is allowed or denied access to a resource
  - `Action`: Specific action or actions that will be allowed or denied
  - `Resource`: Specifies the object or objects that the statement covers
  - `Condition` (Optional): specify conditions for when a policy is in effect

Example:
```json
{
  "Version": "2012-10-17",
  "Id": "S3-Accounts-Permission",
  "Statement": [
    {
      "Sid": "1",
      "Effect": "Allow",
      "Principal": {
        "AWS": [
          "arn:aws:iam::123456789012:root"
        ]
      },
      "Action": [
        "s3:ListAllMyBuckets",
        "s3:GetBucketLocation"
      ],
      "Resource": "arn:aws:s3:::*"
    }
  ]
}
```
