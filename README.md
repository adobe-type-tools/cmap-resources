# CMap Resources

This open source project provides the latest CMap resources for Adobe's public character collections.

CMap (*Character Map*) resources are used to unidirectionally map character codes, such as a Unicode encoding form, to CIDs (*Characters IDs*, meaning glyphs) of a CIDFont resource. CMap resources, like CIDFont resources, include a /CIDSystemInfo dictionary that specifies /Registry and /Ordering strings that must match for compatibility between the two resources. In other words, a CMap resource can be used with a CIDFont resource only if their /Registry and /Ordering strings match.

A character collection is sometimes referred to as an **ROS**, which is an abbreviation for the three elements of the /CIDSystemInfo dictionary, specifically the **/Registry** string, the **/Ordering** string, and the **/Supplement** value (an integer). When fully specified, the three elements are separate using single hyphens, such as **Adobe-Japan1-6** (broken down into /Registry = *Adobe*, /Ordering = *Japan1*, and /Supplement = *6*).

Although originally designed for use with CIDFont resources, CMap resources are also used for other purposes, such as by the [AFDKO](https://github.com/adobe-type-tools/afdko) *makeotf* tool for building 'cmap' tables for OpenType fonts when the source font is a CIDFont resource.

## Contents

This project includes the following CMap resources, grouped by character collection:

*Adobe-Identity-0*: Adobe-Identity-0 (Special Purpose)  
*Adobe-CNS1-7*: [Adobe-CNS1-7](https://github.com/adobe-type-tools/Adobe-CNS1/) (Traditional Chinese, including Hong Kong SCS-2016)  
*Adobe-GB1-5*: [Adobe-GB1-5](https://github.com/adobe-type-tools/Adobe-GB1/) (Simplified Chinese)  
*Adobe-Japan1-6*: [Adobe-Japan1-6](https://github.com/adobe-type-tools/Adobe-Japan1/) (Japanese)  
*Adobe-Korea1-2*: [Adobe-Korea1-2](https://github.com/adobe-type-tools/Adobe-KR/raw/master/5093.Adobe-Korea1-2.pdf) (Korean)  
*Adobe-KR-9*: [Adobe-KR-9](https://github.com/adobe-type-tools/Adobe-KR/) (Korean)  
*deprecated/Adobe-Japan2-0*: [Adobe-Japan2-0](https://github.com/adobe-type-tools/Adobe-Japan1/raw/master/5097.Adobe-Japan2-0.pdf) (Japanese, for JIS X 0212-1990 only; Deprecated and replaced by Adobe-Japan1-6)

The *VERSIONS.txt* file specifies the current version of each CMap resource.

Each collection of CMap resources includes a *cid2code.txt* file that provides the mappings for each CID in tabular form. The Adobe-Japan1-6 CMap resources additionally include mapping files for the three JIS standards, JIS X 0208, JIS X 0212, and JIS X 0213, for JIS90- (*-jp90*) and JIS2004-savvy (*-jp04*) implementations. (The deprecated Adobe-Japan2-0 CMap resources include the JIS X 0212 mapping files.)

## CMap Resources Versus 'cmap' Tables

CMap resources should not be confused with 'cmap' tables of sfnt-based fonts, such as OpenType and TrueType. While they are functionally similar, in that both unidirectionally map character codes, a &#x27;[cmap](https://docs.microsoft.com/en-us/typography/opentype/spec/cmap)&#x27; table maps them to GIDs (*Glyph IDs*). For some fonts, such as OpenType fonts that are based on one of these character collections and include every glyph, CIDs can equal GIDs, but it is not guaranteed, thus the importance of the distinction.

## Compiling/Decompiling CMap Resources

The [Perl Scripts](https://github.com/adobe-type-tools/perl-scripts) open source project includes a *cmap-tool.pl* script that can be used to compile and decompile CMap resources.

## More Information

To learn more about CMap resources, please reference [Adobe Tech Note #5099](http://wwwimages.adobe.com/content/dam/Adobe/en/devnet/font/pdfs/5099.CMapResources.pdf), *Developing CMap Resources for CID-Keyed Fonts*, and [Adobe Tech Note #5014](http://wwwimages.adobe.com/content/dam/Adobe/en/devnet/font/pdfs/5014.CIDFont_Spec.pdf), *Adobe CMap and CID Font Files Specification*.

## Getting Involved

Send suggestions for changes to the CMap Resources project maintainer, [Dr. Ken Lunde](mailto:lunde@adobe.com?subject=[GitHub]%20CMap%20Resources), for consideration.
