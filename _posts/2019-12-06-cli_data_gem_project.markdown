---
layout: post
title:      "CLI Data Gem Project"
date:       2019-12-07 03:05:53 +0000
permalink:  cli_data_gem_project
---


When I first began working on this project I decided to build a gem which would scrape data from a https://github.com profile. The data would include elements such as the user's name, annual contributions, a list of their repositories, and initially I wanted to be able to open individual repositories, peer into the repository's files and output the text within them. The last feature on that list proved to be a little more arduous than I had anticipated, and I settled with being able to print an individual repository's commit history. In the future I would like to implement the ability to search through files in a repository, however, it is going to take me some time to figure out the best approach.

As a design decision, I originally wanted each class to be responsible for one task. For example, the scraper class retrieves the data, the github class prints the data, and the CLI class handles commands. I was mostly able to adhere to this decision, although I realized there were times when I needed to format the data coming in. Sometimes it made sense to format it after it was scraped and at other times it made sense to format it prior to being displayed. In retrospect, I would prefer to leave the responsibility of formatting to the scraper class. As a side note, I would also prefer the scraper class to be a singleton as there is only one instance needed.

Overall, I found this experience to be very insightful. This project allowed me to think for myself and find the solutions which I believed to be best. I look forward to my project review and I'm certain I will learn a lot.
