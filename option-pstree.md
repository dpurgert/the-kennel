### pstree
option-**pstree**, 
copy/paste and execute `via terminal` the indented below in order to gather **_system/user process related output_** which may help in trouble-shooting the issue you are having. the "To Share" instructions are [here.](https://github.com/two-dogs/the-kennel/blob/master/to-share.md).
***
`
sudo inxi -U ;
sudo apt install gist ;
(
  date ;
  echo --option-pstree-- ;
  [ -d /sys/firmware/efi ] && echo "EFI boot on HDD" || echo "Legacy boot on HDD" ;
  echo --inxi-start ;
  inxi -c0 -F ;
  echo --inxi-end ;
  echo --start-pstree-- ;
  sudo pstree -ansup ;
  echo --end-pstree-- ;
  date
) > ~/trouble-shoot-history.txt | echo "Done, the log has been saved to ~/trouble-shoot-history.txt" ;
gist-paste -sap ~/trouble-shoot-history.txt  ; echo share link above, looks similar to http://git.io/xxxxx
`
***
 Other Share instructions are [here.](https://github.com/two-dogs/the-kennel/blob/master/to-share.md).
***
