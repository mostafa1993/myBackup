#!/bin/bash
cd
dir1=/media/$USER/‍mova
dir2=/mnt/01D27A573CAB7A20
if [ -d $dir2 ]
then
MOVA=$dir2
if [ -d /media/$USER/MooShi ]
then
xdotool windowsize $(xdotool getactivewindow) 100% 60%
echo -e "\e[93mFrom which partition you'd like to get back-up?\e[36m"
list0="Ubuntu mova Quit"
select choice in $list0
do
case $choice in
################################################################################################
Ubuntu)
#options of deleting files before updating them.
echo -e "\e[93mbefore updating your files, do you need to remove any thing?\e[36m"
list1='applications Documents my.terminal all_files just_update'
select option in $list1
do
case $option in
applications)
rm -r /media/ibiu/MooShi/My.laptop.HDD/Ubuntu/$option
echo -e "\e[31mapplications\e[93m is deleted.\e[36m"
;;
Documents)
rm -r /media/ibiu/MooShi/My.laptop.HDD/Ubuntu/$option
echo -e "\e[31mDocuments\e[93m is deleted.\e[36m"
;;
my.terminal)
rm -r /media/ibiu/MooShi/My.laptop.HDD/Ubuntu/$option
echo -e "\e[31mmy.terminal\e[93m is deleted.\e[36m"
;;
all_files)
rm -r /media/ibiu/MooShi/My.laptop.HDD/Ubuntu
echo -e "\e[31mall files\e[93m are deleted.\e[36m"
;;
just_update)
echo -e "\e[93mOK $USER, we'll just update. Please wait a few minutes\e[0m"
break
;;
esac
done
###############
test -d /media/ibiu/MooShi/My.laptop.HDD/Ubuntu
if [ $? -eq 1 ]
then
mkdir /media/ibiu/MooShi/My.laptop.HDD/Ubuntu
fi
###############
#end of options of deleting files.
cp -urv /home/$USER/[^e^T^b^.^~]* /media/ibiu/MooShi/My.laptop.HDD/Ubuntu #> ~bckp.report
cp1_report=$?
cp -urv /home/$USER/.{bashrc,bash_history,root_hist,python_history} /media/ibiu/MooShi/My.laptop.HDD/Ubuntu #>> ~bckp.report
cp2_report=$?
#checking whether the above commands ran correctly or not.
if [ $cp1_report -eq 0 ] && [ $cp2_report -eq 0 ]
then
echo -e "\e[92mDear $USER your files are successfully UPDATED on MooShi"
else
echo "OOPS $USER, there's some errors, check it asap."
#detecting where the error has occured exactly.
case 1 in
$cp1_report)
echo "error is related to \"cp_report1\"."
;;
$cp2_report)
echo "error is related to \"cp_report2\"."
;;
esac
#end of detection proccess.
fi
. /home/ibiu/my.terminal/~backup
break
;;
################################################################################################
mova)
echo -e "\e[93mOK $USER, we'll just update. Please wait a few minutes\e[0m"
cp -urv $MOVA/_Private_ /media/ibiu/MooShi
cp -urv $MOVA/Audio /media/ibiu/MooShi
cp -urv "$MOVA/Applications/Raw_App" /media/ibiu/MooShi/Applications
cp -urv "$MOVA/Text Files" /media/ibiu/MooShi/
echo -e "\e[92mDear $USER your files are successfully UPDATED on MooShi"
. /home/ibiu/my.terminal/~backup
break
;;
################################################################################################
Quit)
echo -e "\e[95mSee you soon $USER.\e[0m"
break
;;
################################################################################################
esac
done
#
else
echo -e "\e[91mMooShi is not availavle...\nplease insert the proper media and try again babe...\e[0m"
fi
################################################################################################
else
echo -e "\e[91mmova is not mounted...\nplease mount mova and try again babe...\e[0m"
fi
