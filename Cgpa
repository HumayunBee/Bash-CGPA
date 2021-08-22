clear
i="y"
echo "Enter name of Database"
read db 
while [ $i="y" ]
do
clear
echo "1.View the data base"
echo "2.view specific Records"
echo "3.Add Record"
echo "4.Exit"
echo "Enter your Choice"
read ch
case $ch in 
	1)cat $db;;
	2)echo "Enter Id "
	  read id 
		grep -i "$id" $db;;
	3)echo "Enter Student id "
	read tid
	echo "Enter Name"
	read tnm
declare -a code;
declare -a mark;
sum1=0
c=1

echo "How many Subject?"
read sub
for ((number=0;number < $sub;number++))
{
echo "Enter Subject Code"
read code[$number]
echo "Enter Marks"
read mark[$number]
if (( "${mark[$number]}" < "40" ))
then
	echo "Grade F"
	c=0
	Point=0

elif (( "${mark[$number]}" < "45" ))
then
	echo "Grade D"
	Point=2
	
elif (( "${mark[$number]}" < "50" ))
then
	echo "Grade c"
	Point=2.25
	
elif (( "${mark[$number]}" < "55" ))
then
	echo "Grade C+"
	Point=2.5

elif (( "${mark[$number]}" < "60" ))
then
	echo "Grade B-"
	Point=2.75
	
elif (( "${mark[$number]}" < "65" ))
then
	echo "Grade B"
	Point=3

elif (( "${mark[$number]}" < "70" ))
then
	echo "Grade B+"
	Point=3.25
	
elif (( "${mark[$number]}" < "75" ))
then
	echo "Grade A-"
	Point=3.5

elif (( "${mark[$number]}" < "80" ))
then
	echo "Grade A"
	Point=3.75

else
	echo "Grade A+"
	Point=4

fi
sum1=`bc <<< "scale=2;$sum1 + $Point"`

}
fpoint=`bc <<< "scale=2;$sum1 / $sub"`

if (( "$c" == "1" ))
then 
if (( $(echo "$fpoint < 2.00" | bc -l)))
then 
	grade=F
	echo "Your CGPA $grade"
	

elif (( $(echo "$fpoint < 2.25" | bc -l)))
then 
	grade=D
	echo "Your CGPA $grade"
	
elif (( $(echo "$fpoint < 2.50" | bc -l)))
then 
	grade=C
	echo "Your CGPA $grade"

elif (( $(echo "$fpoint < 2.75" | bc -l)))
then 
	grade=C+
	echo "Your CGPA $grade"

elif (( $(echo "$fpoint < 3.00" | bc -l)))
then 
	grade=B-
	echo "Your CGPA $grade"
	
elif (( $(echo "$fpoint < 3.25" | bc -l)))
then 
	grade=B
	echo "Your CGPA $grade"
	
elif (( $(echo "$fpoint < 3.50" | bc -l)))
then 
	grade=A+
	echo "Your CGPA $grade"

elif (( $(echo "$fpoint < 3.75" | bc -l)))
then 
	grade=A-
	echo "Your CGPA $grade"
	
elif (( $(echo "$fpoint < 4.00" | bc -l)))
then 
	grade=A
	echo "Your CGPA $grade"
else 
	grade=A+
	echo "Your CGPA $grade"
	
fi 
else
	grade=F
	echo "Gpa $grade"
	
fi
	echo "$tid $tnm $fpoint $grade ">>$db;;
	*)echo "Invalid Choice";;
	esac
echo "Do u Want To Continue ? y or n "
read i
if [ $i != "y" ]
then 
	exit 
fi
done
