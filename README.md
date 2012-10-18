# Ec2::Blackout

Want to reduce your EC2 costs?

Do you stop EC2 instances out of business hours?

If you don't, `ec2-blackout` could save you money

`ec2-blackout` is a command-line tool to stop running EC2 instances.

Use ec2-blackout to shutdown EC2 instances when they are idle, for example when you are not in the office.

Certinaly not suitable for production instances but development and test instances can generally be shutdown overnight to save money.

## Installation

    $ gem install ec2-blackout

It is recommended you create an access policy using Amazon IAM

1. Sign in to your AWS management console and go to the IAM section
2. Create a group and paste in the following policy

    {
      "Statement": [
        {
          "Action": [
            "ec2:StartInstances",
            "ec2:StopInstances"
            "ec2:CreateTags",
            "ec2:DeleteTags",
            "ec2:DescribeInstances"
            "ec2:DescribeRegions"
          ],
          "Effect": "Allow",
          "Resource": \[
            "\*"
          \]
        }
      ]
    }

3. Create a user account and download the access key.
4. Add the user to the previously created group.


Once installed you need to export your AWS credentials

    export AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY
    export AWS_SECRET_ACCESS_KEY=YOUR_SECREY_KEY

## Usage

    $ ec2-blackout --help



## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
