# Lab-12

## WHAT WE'RE DOING

Going through a laundry list of stuff.
I love laundry:

- [ ] quota issues - my bad
- [ ] looking at CSV files to guide your coding
- [ ] bringing back longer error messages for test runs
- [ ] the FileHandler constructor
- [ ] you might need to look into the Picture source
- [ ] assignment 5 late policy
- [ ] info about the Gauntlet
- [ ] last drill out today. Cry not.

---

## QUOTA ISSUES

So there is a hidden folder in many of the assignment directories that you need to get rid of, because each one has a large number of files and folders that are counting against your quota on INS.

To find out where these folders are located, go to your home directory on INS and enter in the following command: `find . -name .git`

You then need to delete each of these .git folders. (If you can't remember how to do that, go back and look at the [Linux Command Reference](https://bit.ly/mru-1501-linux-ref) back in Lab-00.)

## GUIDING CODE WITH CSV TEST FILES

If you look in the `tests` directory of the assignment directory, you'll see a data directory:
<pre>
├── data
│   ├── ArtiiApp
│   │   └── console.csv
│   ├── AsciiArt
│   │   ├── charAt.csv
│   │   ├── getHeight.csv
│   │   ├── getName.csv
│   │   ├── getNumChars.csv
│   │   ├── getUniqueChars.csv
│   │   ├── getWidth.csv
│   │   └── toString.csv
│   ├── AsciiToPngConverter
│   │   └── saveHexColorsToDisk.csv
│   ├── CharToColorMap
│   │   └── colorFor.csv
│   └── FileHelper
│       ├── asciiArtFilePath.csv
│       ├── hexcolorFilePath.csv
│       ├── isAvailable.csv
│       ├── mapFilePath.csv
│       └── pngFilePath.csv
</pre>

See all those csv files? Notice how they're separated into directories corresponding to the classes you're asked to create? And notice how each one is named after a public method you've been asked to create?

That's no coincidence!

If you look inside those files, you'll see how I test each of those methods. That information is useful to you. For example, if you look inside `FileHelper/mapFilePath.csv`, you'll see:

<pre>
projectRoot, asciiArtName, expectedPath
"foo", "block", "foo/color-map-files/block.map"
"foo", "jagged-block", "foo/color-map-files/jagged-block.map"
"foo", "one-row", "foo/color-map-files/one-row.map"
"foo", "one-col", "foo/color-map-files/one-col.map"
"foo", "one-pixel", "foo/color-map-files/one-pixel.map"
"foo", "cake", "foo/color-map-files/cake.map"
</pre>

The first row is just a description of what the columns are in this csv: in this case **projectRoot**, **asciiArtName**, and **expectedPath**. The next rows are what are used to test the mapFilePath method. So the first test creates a new FileHelper object, calling `new FileHelper("foo")`. It then calls `mapFilePath("block")` and expects the String `"foo/color-map-files/block.map"` to be returned.

## BRINGING BACK LONGER ERROR MESSAGES

The `Makefile` file in every assignment directory we've used up to now is what makes things like `make run` work.

In the last assignment, I tweaked the Makefile to stop showing all the error details that occurred when your tests failed - this was a bit shortsighted of me, because those error messages were useful for debugging sometimes.

If you want to get the verbose messages back, open up the Makefile in emacs and then comment out the `| grep` parts that are there.

For example, you want to make this line:

<pre>
        java -jar $(JUNIT_LOCATION) --class-path bin:tests:$(ASSERTJ_LOCATION) --scan-class-path --details tree | grep "│"
</pre>

into this:

<pre>
        java -jar $(JUNIT_LOCATION) --class-path bin:tests:$(ASSERTJ_LOCATION) --scan-class-path --details tree # | grep "│"
</pre>

See the change? We've put a hash (`#`) after the `tree`.


## FILEHANDLER CONSTRUCTOR

Constructors are meant to initialize the state of the object being created.

The state of an object is its instance variables.

What are the instance variables of FileHandler?....

## PICTURE SOURCE

If you're working on the **AsciiArt** class, you should carefully read the [notes for Picture](https://github.com/MRU-CSIS-1501/201804.asg.05.documentation/blob/master/notes.for.Picture.java.md). If you don't, creating the png and hexcode files will be soooooo frustrating.

## A5 LATE POLICY

According to the [Academic Schedule Policy](https://drive.google.com/file/d/0B2rB1ncpgWxvblczZFV3WVJrWm8/view), section C.1.4:
> "All course work (assignments and examinations) must be completed within the
course start and end dates specified.", meaning that there is no late option for the final assignment.

Translation: there will be no lates accepted for the last assignment.

## THE GAUNTLET

<pre>
gaunt·let
/ˈɡôntlət,ˈɡäntlət/
noun

1. go through an intimidating or dangerous crowd, place, or experience in order to reach a goal.
"they had to run the gauntlet of television cameras"
2. HISTORICAL
undergo the military punishment of receiving blows while running between two rows of men with sticks.
</pre>

You wanna study? Have I got a deal for you: more than 40 coding questions of all shapes, sizes, genders, and lengths that you can work through to find your weak spots and make you beg for mercy.

Starting Friday, December 8, the Gauntlet will be available on INS. 

Burn through as many questions as you can between before the final exam. Challenge your friends. Challenge your enemies. Do speed runs. Whatever it takes - just practice until your eyes bleed.

## YOUR (LAST!) SKILL DRILL

The following is due by 9AM on December 4th:

- lab-11 : odds and evens

That's it. No more drills. Stop grinning.
