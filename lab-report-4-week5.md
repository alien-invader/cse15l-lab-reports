Search any line that contains the word in filename on Linux:
grep 'word' filename
Perform a case-insensitive search for the word ‘bar’ in Linux and Unix:
grep -i 'bar' file1
Look for all files in the current directory and in all of its subdirectories in Linux for the word ‘httpd’:
grep -R 'httpd' .
Search and display the total number of times that the string ‘nixcraft’ appears in a file named frontpage.md:


# Lab Command - `grep`


## `grep -r` : Searching for a string recursively in all directories

grep -r will look for all files in the current directory and in all of its subdirectories. 

> Example 1:

grep -r searches for the string "2025" in all its directories and subdirectories. For example, `./government` is a subdirectory of `./technical/`,  `Env_Prot_Agen/` is a subdirectory of `./government` and `multi102902.txt` is a text file under `Env_Prot_Agen/`. The output not only includes the filename of the file that contains the string, but also prints the content of the line of the word. 

Command:

    elainege@Elaines-MacBook-Air-2 technical % grep -r 2025

Output:

    ./government/Env_Prot_Agen/multi102902.txt:2025 tons for a situation in which the boilers required separate
    ./government/Gen_Account_Office/Testimony_cg00010t.txt:1955 1965 1975 1985 1995 2005 2015 2025 2035 2045 2055 2065
    ./government/Gen_Account_Office/Testimony_cg00010t.txt:is projected to face insolvency in 2025. Social Security
    ./government/Gen_Account_Office/d01591sp.txt:2000 2005 2010 2015 2020 2025 2030 2035 2040 2045 2050
    ./government/Gen_Account_Office/d01591sp.txt:2000 2005 2010 2015 2020 2025 2030 2035 2040 2045 2050
    ./government/Gen_Account_Office/d01591sp.txt:2000 2025 2050 2075
    ./government/Gen_Account_Office/og96045.txt:hydrocarbon emissions by the year 2025, such a reduction will also
    ./government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:0.600000 0 5 1015202530354045
    ./biomed/1471-2156-4-9.txt:          the corresponding cDNAs (LD20253, obtained from Genome

> Example 2:

grep -r searches for the string "2020" in `./biomed` as I specified after the string. The format is grep -r "String" “Filename or Directory”. It searches recursively under the directory. I noticed that by searching  `2020`, we can find `ATH1.pep.03202001` where 2020 is embedded in a word. I learned that the input string doesn't necessarily has to be a word, it can also be a substring of a word. 

Command: 

    elainege@Elaines-MacBook-Air-2 technical % grep -r 2020 biomed 

Output:

    biomed/1471-2105-3-14.txt:          ATH1.pep.03202001, a flatfile database of 25,579 
    biomed/1471-2105-3-14.txt:          ATH1.pep.03202001 and wormpep 43 against Pfam 6.6. Only
    biomed/1471-2105-3-14.txt:          (58%) sequences from ATH1.pep.03202001 could be assigned
    biomed/1471-2105-3-14.txt:          ATH1.pep.03202001 "as putative cinnamyl-alcohol
    biomed/1471-2202-2-19.txt:          laminin-1 (30 nM, Sigma L2020), 2 hours with 10%
    biomed/1471-2202-3-10.txt:          Sigma, L-2020), agrin (1:40, courtesy of Dr. Herman

> Example 3: 

grep -r searches for the string "Manhattan" in all its directories and subdirectories. For example, `./government` is a subdirectory of `./technical/`,  `Gen_Account_Office//` is a subdirectory of `./government` and `d01376g.txt` is a text file under `Gen_Account_Office/`. The output not only includes the filename of the file that contains the string, but also prints the content of where the word is, the line that the word is in. It is case sensitive. 

Command:

    elainege@Elaines-MacBook-Air-2 technical % grep -r Manhattan
Ouput:

    ./government/Gen_Account_Office/d01376g.txt:Chase Manhattan Bank
    ./government/Gen_Account_Office/ai00134.txt:Chase Manhattan Corporation 18,656
    ./government/Gen_Account_Office/ai00134.txt:Chase Manhattan Corporation $18,656,000 $628,846 $1,168,750
    ./government/Gen_Account_Office/ai00134.txt:Administration The Chase Manhattan Bank
    ./government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:borough of Manhattan for New York
    ./government/Media/Owning_a_Piece.txt:agency's Church Street building in Lower Manhattan, which was
    ./government/Media/Terrorist_Attack.txt:Manhattan and literally pulled the plug on the first official news
    ./government/Media/Terrorist_Attack.txt:at the Manhattan campus of Fordham University School of Law.
    ./government/Media/Terrorist_Attack.txt:City Bar and by emergency consortia of large Manhattan firms to
    ./government/Media/Poverty_Lawyers.txt:counterparts at big Manhattan firms: $6,500 and $7,500,
    ./government/Media/Poverty_Lawyers.txt:28, a criminal defense staff attorney at Manhattan Legal Aid. "So
    ./government/Media/Crains_New_York_Business.txt:analysis by Manhattan-based real estate brokerage TenantWise.com
    ./plos/pmed.0020059.txt:          zip-code areas in southern Bronx and northern Manhattan. This signal had 63 cases
    ./plos/pmed.0020059.txt:          centered in northern Manhattan occurred at the peak of this citywide outbreak. Laboratory
    ./plos/pmed.0020059.txt:          hospitals in southern Bronx and northern Manhattan, with null occurrence rates of 1.6 and
    ./plos/pmed.0020059.txt:          Manhattan on 28 November with a null occurrence rate of once every 2.7 y. On each of the
    ./plos/pmed.0020059.txt:        to northern Manhattan.
    ./plos/journal.pbio.0020150.txt:        lab. “We are a long way from making a working polygraph,” he says. Even with a “Manhattan
    ./biomed/gb-2002-3-7-research0036.txt:          clustered, such as the Euclidean or Manhattan distance
    ./biomed/1471-2377-1-2.txt:        data from Northern Manhattan suggest that blacks are not
    ./biomed/1471-2377-1-2.txt:        Manhattan, New York; Greater Cincinnati/Northern Kentucky).
    ./biomed/1471-2377-3-4.txt:            adopted a modification of the Northern Manhattan Stroke
    ./911report/chapter-13.5.txt:            70. For other officers' positioning, see NYPD interview 20, Manhattan SouthTask Force
    ./911report/chapter-13.5.txt:            145. NYPD interview 20, Manhattan SouthTask Force (May 4, 2004); NYPD interview 21,
    ./911report/chapter-13.5.txt:            162. For the FDNY boat radioing of the collapse, see FDNY recording, FDNY Manhattan
    ./911report/chapter-13.5.txt:            184. NYPD interview 20, Manhattan SouthTask Force (May 4, 2004); NYPD interview 21,
    ./911report/chapter-13.5.txt:                coated Lower Manhattan with a thick layer of dust from the debris and fire. For days
    ./911report/chapter-13.5.txt:                issued five press releases regarding air quality in Lower Manhattan. A release on
    ./911report/chapter-13.5.txt:                Lower Manhattan after 9/11. The EPA and the White House therefore improvised and
    ./911report/chapter-1.txt:    The controllers observed the plane in a rapid descent; the radar data terminated over Lower Manhattan. At 9:03, United 175 crashed into the South Tower.
    ./911report/chapter-1.txt:    By 9:08, the mission crew commander at NEADS learned of the second explosion at the World Trade Center and decided against holding the fighters in military airspace away from Manhattan:
    ./911report/chapter-1.txt:    Mission Crew Commander, NEADS: This is what I foresee that we probably need to do. We need to talk to FAA. We need to tell 'em if this stuff is gonna keep on going, we need to take those fighters, put 'em over Manhattan. That's best thing, that's the best play right now. So coordinate with the FAA. Tell 'em if there's more out there, which we don't know, let's get 'em over Manhattan. At least we got some kind of play.
    ./911report/chapter-1.txt:    The FAA cleared the airspace. Radar data show that at 9:13, when the Otis fighters were about 115 miles away from the city, the fighters exited their holding pattern and set a course direct for Manhattan. They arrived at 9:25 and established a combat air patrol (CAP) over the city.
    ./911report/chapter-9.txt:                operations in Lower Manhattan. The repeater system was installed at the Port
    ./911report/chapter-9.txt:                appropriate borough (in this case, Manhattan). Transfers were often plagued by
    ./911report/chapter-9.txt:                Manhattan arrived and took over. Both chiefs immediately began speaking with the
    ./911report/chapter-9.txt:                specific floors. According to Division Chief for Lower Manhattan Peter Hayden, "We
    ./911report/chapter-9.txt:                into Manhattan.
    ./911report/chapter-9.txt:            The South Tower's total collapse was immediately communicated on the Manhattan
    ./911report/chapter-12.txt:                level Lower Manhattan.
    ./911report/chapter-10.txt:                    health advice to give about the air quality in Lower Manhattan in the vicinity 


## Perform a search ignore the case sensitivity

## Count the lines where strings are matched with -c option
