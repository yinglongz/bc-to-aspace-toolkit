BASE=2010-nps-emails
IMAGE=$(BASE).dmg
ZIP=$(BASE).zip

FILES=*/ Makefile

$(IMAGE) iso dmg:
	/bin/rm -f $(IMAGE) *~ .DS_Store
	hdiutil create $(IMAGE) -fs MS-DOS -size 10m -volname TESTDISK
	hdiutil mount $(IMAGE)
	cp -rv $(FILES) /Volumes/TESTDISK
	hdiutil unmount /Volumes/TESTDISK
	mv 2010-nps-emails.dmg 2010-nps-emails.raw
	/bin/rm 2010-nps-emails.aff 2010-nps-emails.E01
	affconvert 2010-nps-emails.raw
	ewfacquire -c best -u 2010-nps-emails.raw

$(ZIP) zip:
	/bin/rm -f $(ZIP)
	zip -r $(ZIP) $(FILES)
