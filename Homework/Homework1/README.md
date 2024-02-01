1.  mkdir original_zips
mv *.zip original_zips/

2. head -n 1 HousingPrices.csv > file1.csv
head -n $(($(wc -l < HousingPrices.csv) / 3)) HousingPrices.csv | tail -n +2 >> file1.csv

head -n 1 HousingPrices.csv > file2.csv
head -n $(($(wc -l < HousingPrices.csv) * 2 / 3)) HousingPrices.csv | tail -n +$((($(wc -l < HousingPrices.csv) / 3) + 2)) >> file2.csv

head -n 1 HousingPrices.csv > file3.csv
tail -n $(($(wc -l < HousingPrices.csv) / 3)) HousingPrices.csv >> file3.csv

3. head -n 1 HousingPrices.csv > presence.csv
grep "Presence" HousingPrices.csv >> presence.csv

head -n 1 HousingPrices.csv > absence.csv
grep "Absence" HousingPrices.csv >> absence.csv

4. head -n 1 HousingPrices.csv > presence.csv
grep "Presence" HousingPrices.csv >> presence.csv

head -n 1 HousingPrices.csv > absence.csv
grep "Absence" HousingPrices.csv >> absence.csv
