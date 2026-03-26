# Moodle IPA Filter #

[![Build Status](https://travis-ci.org/kwiliarty/moodle-filter_ipa.svg?branch=master)](https://travis-ci.org/kwiliarty/moodle-filter_ipa)

[Source URL](https://github.com/kwiliarty/moodle-filter_ipa.git)

The Moodle IPA Filter displays [X-SAMPA](http://en.wikipedia.org/wiki/X-sampa) as unicode IPA. The intent is to
offer an easy and fast way to display the [International Phonetic Alphabet](http://www.langsci.ucl.ac.uk/ipa/) in Moodle.

## Installing the filter ##

1. Download the latest version of the Moodle IPA Filter and put the ipa folder in Moodle at /filter/ipa.
2. **OR...** From your main Moodle directory: `git clone https://github.com/kwiliarty/moodle-filter_ipa.git filter/ipa`
3. In Moodle go to *Site administration > Notifications* and install the filter
4. Next go to *Site Administration > Plugins > Filters > Manage Filters*
5. Enable the IPA filter (or set it to "Off but available")
6. Test the filter by entering a string such as the following to the content of a label:

    -{D@ "fIlt@r Iz "w@rkIN}-

## Fonts ##

In order to ensure that the IPA displays correctly -- especially the combining marks (diacritics) -- you will want to be
loading at least one fully compatible web font. The Moodle IPA filter ships with two fonts that you can call, or you can
use a carefully selected Google Web Font. In each case you will need to add a link to a particular style sheet in the HEAD
area of *Site administration > Appearance > Additional HTML*.

### [Gentium](http://scripts.sil.org/cms/scripts/page.php?item_id=Gentium_download) ###

Gentium is the first font listed in the 'font-family' so it is the font that will display even if you call more than one.
Gentium is a slightly fanciful serif font that is very readable even at smaller sizes -- important when you are using
unusual glyphs. [Sample](http://scripts.sil.org/cms/scripts/page.php?item_id=Gentium_samples)

To use Gentium add something like this to your *Additional HTML*:

    <link rel="stylesheet" href="URL_TO_YOUR_MOODLE/filter/ipa/gentium.css" type="text/css">

You will need to provide the URL to your own Moodle site as the first part of the href.

### [Doulos](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&item_id=DoulosSIL_download) ###

Doulos is a somewhat compact serif font without unnecessary flourishes. Doulos is listed second in the 'font-family'.
[Sample](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=DoulosSILfont)

To use Doulos add a line like this to your *Additional HTML*:

    <link rel="stylesheet" href="URL_TO_YOUR_MOODLE/filter/ipa/doulos.css" type="text/css">

### [Tinos](http://www.google.com/fonts/specimen/Tinos) ###

Tinos is a stylish serif font and one of only a couple Google Web Fonts that handles the spacing for the combining marks
well. To use Tinos you would add a line like this to your *Additional HTML*:

    <link rel="stylesheet" href="URL_TO_YOUR_MOODLE/filter/ipa/tinos.css" type="text/css">

## Usage ##

Enclose X-SAMPA in curly braces with hyphens outermost: "-{" opens a stretch of X-SAMPA, and "}-" closes the stretch.

## Updates #

As of March 2026 original repository is archived and no longer maintained. The filter is now maintained for University of Valladolid needs in a forked repository at https://github.com/juacas/moodle-filter_ipa. The following updates have been made to the filter code to modernize it and ensure compatibility with current Moodle versions:

Summary of Changes
✅ Created new class file: text_filter.php

Renamed filter_ipa class to text_filter
Added proper namespace namespace filter_ipa
Moved the entire filter implementation to this new location
Updated internal references to use the mappings class from the same namespace
✅ Updated filter.php

Removed the deprecated class definition
Added a class_alias for backward compatibility with code that may still reference the old filter_ipa class
✅ Updated lib.php

Added namespace filter_ipa declaration
Renamed filter_ipa_mappings class to mappings
Added a class_alias for backward compatibility with code using the old filter_ipa_mappings class name
The filter now follows Moodle's modern class naming convention with the fully-qualified class name \filter_ipa\text_filter while maintaining backward compatibility with existing code that uses the deprecated names.