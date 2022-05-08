# find-total-number-of-files-and-directories-in-agiven-path
#!/bin/bash
path=(`echo $ PATH  | tr ":" "\n")
count=0
for i in ${path[@]}
do
cd $i
files=(` echo *` )
for j in ${files[@]}
do 
if [ -x $j ]
then
count=$(($count+1))
fi
done
echo "current dir: $i "
echo "current count : $count "
done
echo "total : $count"
