# Host a Website on AWS

This project will guide you through setting up a personal website using Amazon S3 and connecting it with a custom domain through Amazon Route 53.

## Steps

### Step 1: Design Your Website
- Design your website or download an existing template from the internet.

### Step 2: Set Up the Amazon S3 Bucket
1. Go to the [AWS Management Console](https://aws.amazon.com/console/) and open the Amazon S3 console.
2. Click **Create bucket** and enter a globally unique name for your bucket.
3. In the **Properties** section, enable **Static website hosting**.
4. Upload your website files to the bucket.
5. Set the bucket permissions to allow public access.

### Step 3: Purchase a Custom Domain through Amazon Route 53
1. Open the [Amazon Route 53 console](https://console.aws.amazon.com/route53/).
2. Choose **Domain registration** and then **Register domain**.
3. Follow the prompts to purchase your custom domain.
4. In the **Route 53 hosted zones**, create a new record set.
5. Enter your S3 bucket's endpoint as the alias target.

## Additional Resources
- [AWS S3 Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
- [Amazon Route 53 Documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html)

Feel free to reach out if you have any questions or need further assistance.

