# Automatic-ALT-Text-Generator
This script written in to generate ALT text in bulk. Basically the script reads the excel file and passes the URL to Microsoft Azure Computer Vision API. The output is an excel file with with ALT text for each image URLs. 

#Dependencies
Microsoft Azure Computer Vision
Pandas

#How to install azure computer vision:
pip install azure-cognitiveservices-vision-computervision

#Get your Microsoft Azure Credentials
For this script to function you need to have Azure account. You can use FREE account that will provide 5000 transactions per month.
Goto: https://portal.azure.com/ and create an account
After creating an account login to your account
Click on create a resource
Search for computer vision 
Use free or paid subscription plan
Create a resource group
Name your resource
Select pricing tier
Click on review and create
If everything works fine, your resource will be created
Goto the homepage and click on newly created resource 
Click on Keys and Endpoint under Resource Management to grab your Key1 and Endpoint

#How to use the script
For the script to function you need to have your Azure keys and endpoint
Upload the excel file to the notebook
Include your excel file path in this variable: excel_file
This script is reading only .csv file. To make it read .xlsx you can change df_excel = pd.read_csv(excel_file) to df_excel = pd.read_excel(excel_file)
Make sure your excel file has the column named 'Image URL' where all the urls of the image are stored row wise. You can also change:- urls = df_excel['Image URL'].values to urls = df_excel['YOUR COLUMN NAME'].values 
The output will be stored in final_df.to_excel('/content/output.xlsx', index = False)
Please make sure you delete the output file each time you run the script.

#The Output
The output will be the excel file containing images urls and its respective Generated ALT text for each images as well as confidence level for each generated ALT text
