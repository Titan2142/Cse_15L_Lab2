# Lab Report 2

Our first idea was to compile and run the MarkdownParse.java file to see what type of erro we would get.

After running, we saw the compiler copiled, so there was no compile error. Then, we noticed that the program wouln't stop running, indicating a infinite loop.

![commit1](https://user-images.githubusercontent.com/102689054/165003577-ee17d583-6dec-4260-9882-42b1f7160381.PNG)

Our first idea was to confirm if there was an infinite loop, by printing out the currentIndex integer.

![index error](https://user-images.githubusercontent.com/102689054/165003692-e48c1c80-b8b4-43fa-bb2f-777fb9d94635.PNG)

Sure enough, there was a infinite loop, the currentIndex was constantly cycling between two different numbers.

We createad a new testFile with one link inside to see if the issued continued
![newTest](https://user-images.githubusercontent.com/102689054/165004142-1c144eda-cbf3-4be4-b337-cfe4c739cd04.PNG)
That time it correctly printed, with no issues. So we went back to the original test file tosee what was different.

![Test file](https://user-images.githubusercontent.com/102689054/165003703-8a2dc5aa-ab59-4b65-9469-19de33d15b07.PNG)
We saw, there was an empty line at the end, causing the currentIndex to reset to -1, keeping the while loop going.

![commit2](https://user-images.githubusercontent.com/102689054/165003587-f475e3d7-b5e4-4537-9f96-d301ef350c12.PNG)
we added a if statement to check if any of the variables would equal -1 to break the loop.




![commit3](https://user-images.githubusercontent.com/102689054/165003592-eca11e5e-06f3-4e51-b0ff-d4a9d02dde28.PNG)
In case a image file were loaded, we added a check if a "!" were ever stored to continue the while loop, to prevent it from crashing if a imageis passed through


