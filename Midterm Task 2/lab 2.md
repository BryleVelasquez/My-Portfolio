# 𝐌𝐢𝐝𝐭𝐞𝐫𝐦 𝐋𝐚𝐛 𝐓𝐚𝐬𝐤 𝟐: 𝐃𝐚𝐭𝐚 𝐂𝐥𝐞𝐚𝐧𝐢𝐧𝐠 𝐚𝐧𝐝 𝐓𝐫𝐚𝐧𝐬𝐟𝐨𝐫𝐦𝐚𝐭𝐢𝐨𝐧 𝐔𝐬𝐢𝐧𝐠 𝐏𝐨𝐰𝐞𝐫 𝐐𝐮𝐞𝐫𝐲 𝐄𝐝𝐢𝐭𝐨𝐫
To extract useful information from the file UncleanedDSJObs.csv taken from a Job Posting site available in Kaggle.  
## 𝓞𝓫𝓳𝓮𝓬𝓽𝓲𝓿𝓮𝓼: 
- to find out Which Job Roles pay the highest and least
- to find out What size companies pay the best
- to find out Where Job Roles or Job Titles pay the best and least in a specific state
## 𝓓𝓪𝓽𝓪 𝓢𝓮𝓽 𝓑𝓮𝓯𝓸𝓻𝓮  𝓒𝓵𝓮𝓪𝓷𝓲𝓷𝓰 𝓐𝓷𝓭 𝓣𝓻𝓪𝓷𝓼𝓯𝓸𝓻𝓶𝓪𝓽𝓲𝓸𝓷:
![image](https://github.com/user-attachments/assets/40df216b-3bbe-4073-a47c-d7412e472515)


## 𝓢𝓽𝓮𝓹𝓼 𝓟𝓮𝓻𝓯𝓸𝓻𝓶𝓮𝓭 𝓲𝓷 𝓓𝓪𝓽𝓪 𝓒𝓵𝓮𝓪𝓷𝓲𝓷𝓰 𝓪𝓷𝓭 𝓣𝓻𝓪𝓷𝓼𝓯𝓸𝓻𝓶𝓪𝓽𝓲𝓸𝓷:
- Duplicated the raw data to preserve the original.  
- Cleaned the salary estimate column by removing everything after the "(" symbol.  
- Created Min Sal and Max Sal columns from the salary estimate.  
- Added a new column Role Type to classify jobs as "data scientist", "data analyst", "data engineer", "machine learning engineer", or "other" based on the job title.  
- Corrected the location column with custom states and split it into city and state abbreviation.  
- Replaced incorrect state entries (e.g., "anne rundell" to "ma").  
- Split the company size column to extract MinCompanySize and MaxCompanySize, and removed the word "employees".  
- Replaced invalid or negative values:  
- Competitors: replaced -1 with "n/a".  
- Revenue: replaced negatives with 0.  
- Industry: replaced -1 with "other".  
- Cleaned company name by removing extra ratings or numbers at the end.  
- Removed unnecessary columns like job descriptions.  
- Duplicated the cleaned data as Sal By Role Type dup, selected Role Type, Min Sal, and Max Sal, converted salaries to currency, multiplied by 1000, and grouped by - Role Type to get average salaries.  
- Created a reference as Sal By Role Size ref, selected Size, Min Sal, and Max Sal, multiplied salaries by 1000, and grouped by Size to get average salaries.  
- Imported a State Mapping file to map state abbreviations to full state names and merged it with the dataset.  
- Created a reference as Sal By State ref, selected State Full Name, Min Sal, and Max Sal, multiplied salaries by 1000, and grouped by State Full Name to get average salaries.  
- Checked query dependencies to confirm correct relationships.  

## 𝓕𝓲𝓷𝓪𝓵 𝓞𝓾𝓽𝓹𝓾𝓽
### 𝓒𝓵𝓮𝓪𝓷𝓮𝓭 𝓓𝓪𝓽𝓪 ⭐
![cleaned](https://github.com/user-attachments/assets/90b08a6c-6752-49bf-b9a3-1bc94db1586a)

### 𝓢𝓪𝓵 𝓑𝔂 𝓡𝓸𝓵𝓮 𝓣𝔂𝓹𝓮 𝓓𝓾𝓹 ⭐
![02](https://github.com/user-attachments/assets/813828ae-153c-40df-85f2-1dc2a421e3c6)

### 𝓢𝓪𝓵 𝓫𝔂 𝓡𝓸𝓵𝓮 𝓢𝓲𝔃𝓮 𝓡𝓮𝓯 ⭐
![03](https://github.com/user-attachments/assets/4f7f9370-c2ac-4db5-88f7-ca13b170e17f)

### 𝓢𝓪𝓵 𝓫𝔂 𝓢𝓽𝓪𝓽𝓮 𝓡𝓮𝓯 ⭐
![05](https://github.com/user-attachments/assets/918d9573-db3e-44fa-a23a-21cb714f3b09)

### 𝓠𝓾𝓮𝓻𝔂 𝓓𝓮𝓹𝓮𝓷𝓭𝓮𝓷𝓬𝓲𝓮𝓼 ⭐
![query dependencies](https://github.com/user-attachments/assets/044c4320-8233-4763-b535-f87e3fc80f3f)

