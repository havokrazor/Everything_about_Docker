### You will run into this trouble alot where you can't create more container , maybe because of disk space issue or the file within the container being full ###

There's a couple of things you could do , one of them is deleting images that you might not need by using the command

`docker rmi image1 image2 image3`

If any of the container are using one of them , you might need to delete/stop those container before running `docker rmi` or you can forcefully delete it by using `docker rmi -f` but be aware of the data loss.

The second thing you could do is use the command `Docker system prune`. *This command smartly remove useless data that is consuming space in our disk*




