                                        
# 🔍 AWS Resource Tracker Automation

This project provides automation scripts to list key AWS resources such as:

- ✅ S3 Buckets  
- ✅ EC2 Instances  
- ✅ Lambda Functions  
- ✅ IAM Users  
- ✅ VPC Details  

It helps in quickly auditing AWS usage manually or on a schedule using `cron`.

---

## 📁 Scripts

- `resource-tracker1`: AWS resource tracking script using basic AWS CLI
- `resource-tracker2`: Improved version with JSON parsing via `jq`, used for cron execution

---

## 🛠️ Requirements

Make sure you have the following installed:

- AWS CLI (`aws`)
- `jq` (for JSON parsing)
- AWS credentials configured properly

You can configure your credentials like this:

```bash
aws configure
Or set them in the script by adding this before the AWS CLI commands:

bash
Copy
Edit
export AWS_SHARED_CREDENTIALS_FILE=/home/ubuntu/.aws/credentials
export AWS_CONFIG_FILE=/home/ubuntu/.aws/config
🔄 Cron Job Setup
To schedule this script to run automatically:

Step 1: Make the script executable
bash
Copy
Edit
chmod +x ~/cleaned-repo/resource-tracker2
Step 2: Edit the crontab
bash
Copy
Edit
crontab -e
Add the following line to run it every day at 8 AM:

bash
Copy
Edit
0 8 * * * /home/ubuntu/cleaned-repo/resource-tracker2 >> /home/ubuntu/cleaned-repo/cronjob2.log 2>&1
You can modify the time as needed.

Step 3: Verify cron job is running
Check the log file:

bash
Copy
Edit
cat ~/cleaned-repo/cronjob2.log
🔁 Git Workflow
After making changes to your scripts or README:

bash
Copy
Edit
git add .
git commit -m "Updated script and cron job instructions"
git push
📌 Notes for Others Using This Script
If someone else wants to run this script:

Make sure AWS CLI and jq are installed.

Set up AWS credentials (aws configure or export path in script).

Make the script executable:

bash
Copy
Edit
chmod +x ./resource-tracker2
Run manually or set up a cron job as shown above.

✅ Done! Your AWS audit is now automated and logged daily.
Happy Automating! 🚀

yaml
Copy
Edit

---

### 👉 Now, to save this into your `README.md`:

1. Run:
   ```bash
   nano README.md
Paste everything above (the full markdown content)

Save and exit (Ctrl + O, Enter, then Ctrl + X)

Then commit it:

bash
Copy
Edit
git add README.md
git commit -m "Updated README with full automation instructions"
git push
