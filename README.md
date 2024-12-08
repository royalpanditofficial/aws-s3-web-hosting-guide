# 🌐 AWS S3 Bucket Static Website Hosting

This guide explains how to host a static website on AWS S3 Bucket step by step.

---

## 🖥️ Steps to Host a Static Website on AWS S3

### 1️⃣ Create an S3 Bucket
1. Log in to your **AWS Management Console**.
2. Go to the **S3 Service**.
3. Click on **Create Bucket**.
4. Provide a unique bucket name (e.g., `my-static-website`) and select your preferred region.
5. In the **Bucket Settings**:
   - Uncheck **Block all public access** (you will be asked to confirm this later).
6. Click **Create Bucket**.

---

### 2️⃣ Upload Website Files
1. Open your newly created S3 bucket.
2. Go to the **Upload** tab.
3. Drag and drop your project files (e.g., `index.html`, `style.css`, images, etc.) into the upload area.
4. Click **Upload** to complete the process.

---

### 3️⃣ Enable Static Website Hosting
1. Go to the **Properties** tab of your S3 bucket.
2. Scroll down to **Static website hosting** and click **Edit**.
3. Select **Enable**.
4. In the **Index document** field, enter `index.html` (or the main file of your website).
5. (Optional) In the **Error document** field, you can enter a custom error page, like `404.html`.
6. Click **Save Changes**.

---

### 4️⃣ Set Bucket Permissions
1. Go to the **Permissions** tab of your S3 bucket.
2. In the **Block public access** section, click **Edit**.
3. Uncheck all options to allow public access.
4. Confirm by typing **confirm** in the prompt and click **Save changes**.

---

### 5️⃣ Add a Bucket Policy
1. In the **Permissions** tab, scroll down to **Bucket policy** and click **Edit**.
2. Click on the **Policy Generator** link provided on the page.
3. Fill out the policy generator form as follows:
   - **Select Type of Policy**: S3 Bucket Policy
   - **Effect**: Allow
   - **Principal**: `*` (this allows access to everyone)
   - **Actions**: `GetObject`
   - **ARN**: Paste your bucket ARN (e.g., `arn:aws:s3:::my-static-website/*`).

4. Generate the policy and copy the code.
5. Paste the generated policy in the **Bucket Policy Editor** and click **Save Changes**.

---

### 6️⃣ Access Your Website
1. Go back to the **Properties** tab.
2. In the **Static website hosting** section, copy the **Website endpoint URL**.
3. Open the URL in your browser to see your hosted website.

---

## 📝 Notes
- Ensure your files (like `index.html`) are correctly linked if using CSS, JS, or images.
- Double-check permissions if your website is not loading properly.
- Use a custom domain (optional) by configuring Route 53 and S3 bucket integration.

---

## 🎉 Congratulations!
Your static website is now live and accessible via the **S3 Website URL**. Share it with others and showcase your work!
