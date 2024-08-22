# DeepTGI

DeepTGI Model

## Quick Start (Tested on Linux)

  * Clone deepTGI repository
```
git clone https://github.com/wanglabhku/DeepTGI
```
  * Go to deepTGI repository
```
cd deepTGI
```
  * Create conda environment
```
conda env create -f environment.yml
```
  * activate deepTGI environment
```
conda activate deepTGI
```
 * Extract model files
   > Before running the program, you need to extract the model files from the split archives located in /DeepTGI/test_R. Use the following command to extract the files：
```
unzip /DeepTGI/test_R/pred_nets.zip
```  
  * Update file paths in the code
    > Before running the program, ensure that any file paths used in the code are correctly updated to match your own directory structure. This is important because the default paths in the code may not align with where you have stored the necessary files. To do this, locate the file paths in the Python scripts (e.g., in `main.py`) and modify them to reflect the actual locations of your files on your system.
    > For example, if a file path in the code is `model_path = "/default/path/to/pred_nets/model"`, you should update it to match your directory structure, such as ：
```
pd.read_csv('~/DeepTGI-main/DeepTGI/dataset/bulk_tf.csv')
```
  * Run the program
```
python main.py
``` 
