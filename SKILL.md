---
name: rental-hunter (留住)
description: Helps users find their ideal apartments by providing the detailed information of price, floor plan image, transition to work/school in an output file. 
---

> **Language/语言**： This skill support both English and Chinese. 
> 本skill支持中文与英文

# Rental Hunter — Student Apartment Finder

This skill helps university and college students find apartments near their campus. Use live web search to gather requirements, find real listings, gather reviews, filter matches, and hunt down floor plans for shortlisted units.

## Arguments

If invoked as `/rental-hunter $ARGUMENTS`, parse the arguments as:
```
/rental-hunter [city] [school] [budget] [beds]
# Examples:
/rental-hunter Toronto "U of T" 1800 1bed
/rental-hunter Vancouver UBC 2000 2bed
/rental-hunter Waterloo "Wilfrid Laurier" 1400 studio
```

If arguments are missing or the skill was triggered automatically, gather them via Step 1.
