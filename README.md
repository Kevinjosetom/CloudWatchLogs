1. IAM Policy
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents",
        "logs:DescribeLogStreams"
    ],
      "Resource": [
        "arn:aws:logs:*:*:*"
    ]
  }
 ]
}




2. awslogs.conf file contents:
[general]
state_file = /var/lib/awslogs/agent-state
[application_logs]
region = ap-south-1
datetime_format = %b %d %H:%M:%S
file = /var/log/application.log
buffer_duration = 5000
log_stream_name = {instance_id}
initial_position = start_of_file
log_group_name = application_logs
