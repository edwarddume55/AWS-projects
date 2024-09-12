# Host a Website on AWS

This project will guide you through setting up a personal website using Amazon S3, connecting it with a custom domain through Amazon Route 53, and securing it with an SSL certificate.

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

### Step 4: Set Up an SSL Certificate
1. Go to the [AWS Certificate Manager (ACM) console](https://console.aws.amazon.com/acm/home).
2. Click **Request a certificate**.
3. Choose **Request a public certificate** and click **Next**.
4. Enter your custom domain name (e.g., `example.com` and `www.example.com`).
5. Choose **DNS validation** and click **Next**.
6. Review the request and click **Confirm and request**.
7. ACM will provide DNS records that need to be added to Route 53. Go back to the [Amazon Route 53 console](https://console.aws.amazon.com/route53/) and add the provided CNAME records to your hosted zone.
8. Once the DNS records are verified, the certificate status in ACM will change to **Issued**.

### Step 5: Configure CloudFront for SSL
1. Open the [Amazon CloudFront console](https://console.aws.amazon.com/cloudfront/).
2. Click **Create Distribution** and select **Web**.
3. In the **Origin Settings**, set your S3 bucket as the origin.
4. In the **Default Cache Behavior Settings**, set **Viewer Protocol Policy** to **Redirect HTTP to HTTPS**.
5. In the **Distribution Settings**, select the SSL certificate you created in ACM from the **Alternate Domain Names (CNAMEs)** section.
6. Set **Price Class** as needed, and click **Create Distribution**.
7. After the distribution is created and deployed, update your Route 53 records to point to the CloudFront distribution's domain name.

## Additional Resources
- [AWS S3 Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
- [Amazon Route 53 Documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html)
- [AWS Certificate Manager Documentation](https://docs.aws.amazon.com/acm/latest/userguide/acm-overview.html)
- [Amazon CloudFront Documentation](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)

Feel free to reach out if you have any questions or need further assistance.
