Step-by-Step Guide: Update Your GitHub Secrets to JSON Format
🎯 Your Goal
You have 3 secrets in GitHub that need to be updated to JSON format:
AZURE_AND_TFSTATE
DBX_DEV
DEV_ENV_DETAILS
❓ Do You Need to Delete Old Secrets?
Answer: NO! You will UPDATE them, not delete and recreate.
GitHub allows you to update secret values without deleting them. The workflows will continue to work.
📋 Before You Start - Prepare Your Values
Step 1: Open a Text Editor (Notepad, VS Code, etc.)
Copy this template and fill in YOUR actual values:
TEMPLATE 1 - AZURE_AND_TFSTATE:
{
  "client_id": "REPLACE_WITH_YOUR_CLIENT_ID",
  "client_secret": "REPLACE_WITH_YOUR_CLIENT_SECRET",
  "tenant_id": "REPLACE_WITH_YOUR_TENANT_ID",
  "subscription_id": "REPLACE_WITH_YOUR_SUBSCRIPTION_ID",
  "state_resource_group": "REPLACE_WITH_YOUR_STATE_RG",
  "state_storage_account": "REPLACE_WITH_YOUR_STATE_STORAGE",
  "state_container": "REPLACE_WITH_YOUR_STATE_CONTAINER"
}

TEMPLATE 2 - DBX_DEV:
{
  "workspace_url": "REPLACE_WITH_YOUR_WORKSPACE_URL",
  "token": "REPLACE_WITH_YOUR_DATABRICKS_TOKEN"
}

TEMPLATE 3 - DEV_ENV_DETAILS:
{
  "resource_group": "REPLACE_WITH_YOUR_RESOURCE_GROUP",
  "storage_account": "REPLACE_WITH_YOUR_STORAGE_ACCOUNT",
  "access_connector_id": "REPLACE_WITH_YOUR_ACCESS_CONNECTOR_ID"
}
Step 2: Fill in Your Actual Values
Example of filled template:
AZURE_AND_TFSTATE (filled example):
{
  "client_id": "12345678-1234-1234-1234-123456789abc",
  "client_secret": "abcdef~12345~xyz",
  "tenant_id": "87654321-4321-4321-4321-cba987654321",
  "subscription_id": "11111111-2222-3333-4444-555555555555",
  "state_resource_group": "rg-terraform-state",
  "state_storage_account": "sttfstatedatabricks",
  "state_container": "tfstate"
}

DBX_DEV (filled example):
{
  "workspace_url": "https://adb-1234567890123456.7.azuredatabricks.net",
  "token": "dapi1234567890abcdefghijklmnopqrstuvwxyz"
}

DEV_ENV_DETAILS (filled example):
{
  "resource_group": "rg-databricks-dev",
  "storage_account": "stdevdatalake001",
  "access_connector_id": "/subscriptions/11111111-2222-3333-4444-555555555555/resourceGroups/rg-databricks-dev/providers/Microsoft.Databricks/accessConnectors/dac-dev-uc"
}
Step 3: Validate Your JSON
Before updating GitHub:
Go to: https://jsonlint.com/
Paste each JSON block
Click "Validate JSON"
If you see ✅ "Valid JSON" - you're good!
If you see ❌ errors - fix them (usually missing comma or quote)
Common JSON Mistakes:
❌ Missing comma: "key1": "value1" "key2": "value2"
✅ Correct: "key1": "value1", "key2": "value2"
❌ Trailing comma: "key": "value",}
✅ Correct: "key": "value"}
❌ Single quotes: {'key': 'value'}
✅ Correct: {"key": "value"}
🔄 Update Secret #1: AZURE_AND_TFSTATE
Step 1: Navigate to GitHub Secrets
1. Open your browser
2. Go to: https://github.com/YOUR_ORGANIZATION/YOUR_REPOSITORY
3. Click: Settings tab (top navigation)
4. Left sidebar → Scroll down to "Security" section
5. Click: Secrets and variables
6. Click: Actions
You should now see:
┌─────────────────────────────────────────────┐
│ Actions secrets and variables                │
├─────────────────────────────────────────────┤
│ Tabs: [Secrets] [Variables]                 │
│                                              │
│ Repository secrets (3)                       │
│                                              │
│ AZURE_AND_TFSTATE    [Update] [Remove]      │
│ DBX_DEV              [Update] [Remove]      │
│ DEV_ENV_DETAILS      [Update] [Remove]      │
└─────────────────────────────────────────────┘
Step 2: Click Update Button
Find: AZURE_AND_TFSTATE
Click: [Update] button (on the right side)
Step 3: Update Secret Form Appears
┌─────────────────────────────────────────────┐
│ Update secret                                │
├─────────────────────────────────────────────┤
│                                              │
│ Name                                         │
│ ┌─────────────────────────────────────────┐ │
│ │ AZURE_AND_TFSTATE                       │ │  ← Cannot be changed
│ └─────────────────────────────────────────┘ │
│                                              │
│ Value *                                      │
│ ┌─────────────────────────────────────────┐ │
│ │ ••••••••••••••••••••••••••••••••        │ │  ← Your old value (hidden)
│ │                                         │ │
│ │                                         │ │
│ └─────────────────────────────────────────┘ │
│                                              │
│ [Update secret] [Cancel]                     │
└─────────────────────────────────────────────┘
Step 4: Clear Old Value and Paste New JSON
1. Click inside the "Value" text box
2. Select all text: Ctrl+A (Windows/Linux) or Cmd+A (Mac)
3. Delete all: Press Delete or Backspace
4. Paste your prepared JSON from text editor
What you should paste:
{
  "client_id": "12345678-1234-1234-1234-123456789abc",
  "client_secret": "abcdef~12345~xyz",
  "tenant_id": "87654321-4321-4321-4321-cba987654321",
  "subscription_id": "11111111-2222-3333-4444-555555555555",
  "state_resource_group": "rg-terraform-state",
  "state_storage_account": "sttfstatedatabricks",
  "state_container": "tfstate"
}
Important:
Paste the ENTIRE JSON block (including { and })
Make sure there are NO extra spaces before or after
Do NOT add any comments or extra text
Step 5: Click "Update secret" Button
Click the green button: [Update secret]
Step 6: Confirmation
You should see:
✅ Secret AZURE_AND_TFSTATE was updated
🔄 Update Secret #2: DBX_DEV
Repeat the Same Process:
Find: DBX_DEV in the secrets list
Click: [Update] button
Clear: Old value (Ctrl+A → Delete)
Paste: Your prepared JSON:
{
  "workspace_url": "https://adb-1234567890123456.7.azuredatabricks.net",
  "token": "dapi1234567890abcdefghijklmnopqrstuvwxyz"
}
Click: [Update secret]
Verify: ✅ Secret DBX_DEV was updated
🔄 Update Secret #3: DEV_ENV_DETAILS
Repeat the Same Process:
Find: DEV_ENV_DETAILS in the secrets list
Click: [Update] button
Clear: Old value (Ctrl+A → Delete)
Paste: Your prepared JSON:
{
  "resource_group": "rg-databricks-dev",
  "storage_account": "stdevdatalake001",
  "access_connector_id": "/subscriptions/11111111-2222-3333-4444-555555555555/resourceGroups/rg-databricks-dev/providers/Microsoft.Databricks/accessConnectors/dac-dev-uc"
}
Click: [Update secret]
Verify: ✅ Secret DEV_ENV_DETAILS was updated
✅ Verification - All Secrets Updated
After updating all 3 secrets, you should see:
┌─────────────────────────────────────────────┐
│ Repository secrets (3)                       │
│                                              │
│ Name                     Updated             │
│ ─────────────────────────────────────────   │
│ AZURE_AND_TFSTATE       ⏱️ 1 minute ago     │
│ DBX_DEV                 ⏱️ 2 minutes ago    │
│ DEV_ENV_DETAILS         ⏱️ 3 minutes ago    │
└─────────────────────────────────────────────┘
Check:
[ ] All 3 secrets show recent "Updated" time
[ ] You still see 3 secrets (not deleted, just updated)
[ ] No error messages
🧪 Test Your Updated Secrets
Option 1: Quick Test with GitHub Actions
Create a test workflow to verify JSON parsing works:
Create file: .github/workflows/test-secrets.yml
name: Test Secrets

on:
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Test Parse Azure Secrets
        run: |
          echo "Testing AZURE_AND_TFSTATE..."
          CLIENT_ID=$(echo '${{ secrets.AZURE_AND_TFSTATE }}' | jq -r '.client_id')
          echo "✅ Client ID parsed: ${CLIENT_ID:0:8}..."
          
      - name: Test Parse Databricks Secrets
        run: |
          echo "Testing DBX_DEV..."
          HOST=$(echo '${{ secrets.DBX_DEV }}' | jq -r '.workspace_url')
          echo "✅ Workspace URL parsed: $HOST"
          
      - name: Test Parse Environment Secrets
        run: |
          echo "Testing DEV_ENV_DETAILS..."
          RG=$(echo '${{ secrets.DEV_ENV_DETAILS }}' | jq -r '.resource_group')
          echo "✅ Resource Group parsed: $RG"
Commit and push this file
Go to: Actions tab in GitHub
Click: "Test Secrets" workflow
Click: "Run workflow"
Check: All steps should show ✅ green checkmarks
Option 2: Manual Verification
You can't see secret values after creation, but you can verify by:
Running the test workflow above
Or proceeding to create a Pull Request with your Terraform code
🚨 Troubleshooting
Issue 1: "Unexpected token" Error in Workflow
Cause: Invalid JSON format
Solution:
Copy your JSON value from the secret
Go to https://jsonlint.com/
Paste and validate
Fix any errors shown
Update the secret again with corrected JSON
Issue 2: "jq: error" in Workflow
Error message: jq: error (at <stdin>:1): Cannot index string with string "client_id"
Cause: Secret is not in JSON format, it's plain text
Solution:
Go back to the secret
Click [Update]
Make sure you pasted the ENTIRE JSON including { and }
Example of what you should see:
{
  "client_id": "xxxxx",
  "client_secret": "xxxxx"
}
NOT:
client_id: xxxxx
client_secret: xxxxx
Issue 3: "Cannot parse" Error
Cause: Extra characters or formatting issues
Solution:
Copy your JSON to text editor
Remove any:
Extra spaces before {
Extra spaces after }
Comments like // this is a comment
Any text outside the JSON block
Should be ONLY the JSON, nothing else
Update secret with cleaned JSON
Issue 4: Forgot My Old Values
Don't worry! Your old values are still there until you update them.
To retrieve before updating:
Run a quick GitHub Actions workflow that echoes the values (just for this purpose)
Or check your local notes/password manager
Or contact your admin for the values again
📝 Before and After Comparison
BEFORE (Wrong Format - Don't use this):
Wrong - Plain Text:
AZURE_AND_TFSTATE = 
client_id: xxxxx
client_secret: xxxxx
Wrong - With Comments:
{
  "client_id": "xxxxx",  // my client id
  "client_secret": "xxxxx"
}
Wrong - Missing Quotes:
{
  client_id: xxxxx,
  client_secret: xxxxx
}
AFTER (Correct Format - Use this):
Correct - Valid JSON:
{
  "client_id": "xxxxx",
  "client_secret": "xxxxx",
  "tenant_id": "xxxxx",
  "subscription_id": "xxxxx",
  "state_resource_group": "xxxxx",
  "state_storage_account": "xxxxx",
  "state_container": "xxxxx"
}
✅ Final Checklist
Before proceeding to next steps:
Secrets Updated:
[ ] AZURE_AND_TFSTATE updated to JSON format
[ ] DBX_DEV updated to JSON format
[ ] DEV_ENV_DETAILS updated to JSON format
[ ] All 3 secrets show recent "Updated" timestamp
[ ] Validated all JSON using jsonlint.com
Values Verified:
[ ] All your Azure credentials are correct
[ ] Databricks workspace URL is correct (with https://)
[ ] Databricks token is not expired
[ ] Access Connector ID is complete and correct
[ ] Resource group and storage account names match your Azure resources
Ready to Test:
[ ] Saved all JSON values in secure password manager
[ ] Ready to create GitHub workflows
[ ] Ready to test with Pull Request
🎯 What's Next
After updating your secrets:
Create Terraform files in your repository
Create GitHub workflow files (using the updated ones I provided)
Commit and push to GitHub
Create a Pull Request
Terraform Plan workflow will automatically run and parse your JSON secrets
Review the plan in PR comments
Merge to deploy
💾 Save This Template for Future Reference
Keep this filled template in your password manager:
===========================================
GITHUB SECRETS - JSON FORMAT
Repository: databricks-terraform-uc
Last Updated: [DATE]
===========================================

SECRET 1: AZURE_AND_TFSTATE
{
  "client_id": "YOUR_VALUE",
  "client_secret": "YOUR_VALUE",
  "tenant_id": "YOUR_VALUE",
  "subscription_id": "YOUR_VALUE",
  "state_resource_group": "YOUR_VALUE",
  "state_storage_account": "YOUR_VALUE",
  "state_container": "YOUR_VALUE"
}

SECRET 2: DBX_DEV
{
  "workspace_url": "YOUR_VALUE",
  "token": "YOUR_VALUE"
}

SECRET 3: DEV_ENV_DETAILS
{
  "resource_group": "YOUR_VALUE",
  "storage_account": "YOUR_VALUE",
  "access_connector_id": "YOUR_VALUE"
}
===========================================
📞 Need Help?
If you get stuck at any step:
Invalid JSON: Use https://jsonlint.com/ to validate
Don't know values: Contact your Azure admin
Workflow errors: Check the "Troubleshooting" section above
Other issues: Create a GitHub issue or contact your team
Summary:
✅ You do NOT delete secrets
✅ You UPDATE existing secrets with new JSON values
✅ Use the [Update] button, not [Remove]
✅ Paste complete JSON including { and }
✅ Validate JSON before updating
✅ All 3 secrets remain with same names, just new format
You're ready to update your secrets! 🚀
