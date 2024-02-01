1.  
mkdir original_zips  
mv *.zip original_zips/

2.  
head -n 1 diabetes_prediction_dataset.csv > file1.csv
head -n $(($(wc -l < diabetes_prediction_dataset.csv) / 3)) diabetes_prediction_dataset.csv | tail -n +2 >> file1.csv

head -n 1 diabetes_prediction_dataset.csv > file2.csv
head -n $(($(wc -l < diabetes_prediction_dataset.csv) * 2 / 3)) diabetes_prediction_dataset.csv | tail -n +$((($(wc -l < diabetes_prediction_dataset.csv) / 3) + 2)) >> file2.csv

head -n 1 diabetes_prediction_dataset.csv > file3.csv
tail -n $(($(wc -l < diabetes_prediction_dataset.csv) / 3)) diabetes_prediction_dataset.csv >> file3.csv

3.
head -n 1 Heart_Disease_Prediction.csv > presence.csv
grep "Presence" Heart_Disease_Prediction.csv >> presence.csv

head -n 1 Heart_Disease_Prediction.csv > absence.csv
grep "Absence" Heart_Disease_Prediction.csv >> absence.csv

4.  
total_lines=$(wc -l < car_web_scraped_dataset.csv)
no_accident_lines=$(grep -c "no accidents" car_web_scraped_dataset.csv)
fraction=$(echo "scale=2; $no_accident_lines / $total_lines" | bc)
echo "Fraction of cars with no accidents: $fraction"

5.
sed -e 's/yes/1/g' -e 's/no/0/g' -e 's/unfurnished/0/g' -e 's/semi-furnished/2/g' -e 's/,furnished/,1/g' Housing.csv > Housing_modified.csv

6.  
cut -d ',' -f 2- Mall_Customers.csv > Mall_Customers_noID.csv

7.
* cut -d ',' -f 4,5,6,7 Mall_Customers.csv | tr ',' '+' | bc > sum_scores.csv
* sort -t ',' -k2 -n cancer_patient_data_sets.csv > sorted_cancer_data.csv


