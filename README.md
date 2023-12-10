# Taipan_40_Column_Apple_II
Taipan for low resolution 40 column display on Apple II (***not*** the more common, hi-res, version).

The Applesoft BASIC code from the book,  [TAIPAN - A historical adventure for the Apple Computer (PDF)][1] by *Art Canfil*, *Karl Albrecht*, and *Jim McClenahan*, linked to from [taipangame.com][2].

The code is provided on both a per-chapter basis and as the combined code. 

NOTE: Some typos may remain - the listings in the PDF are able to be copied and pasted but the terrible "digital/chequebook-style" font and formatting used cause a huge number of "OCR_type" typos when pasted.

### Errata from book

#### Tea purchasing

A patch is required due to an omission in the book (page 49), in order to be able to purchase tea: 

```
261 IF X$ = "S" THEN X1 = 1
262 IF X$ = "T" THEN X1 = 2 
263 IF X$ = "A" THEN X1 = 3 
264 IF X$ = "P" THEN X1 = 4 
```

#### Extraneous `V1`

The extraneous `V1` has *already* been removed from line 5040

```
5040 DATA V1 " : "

```
### See also
- [Looking for an accurate Apple II(e) character set - in particular, what is CHR$(133)?][3]
- [Taipan in Applesoft BASIC][4]



  [1]: https://taipangame.com/pdf/TaipanAHistoricalAdventureForTheAppleComputerAppleIIEdition.pdf
  [2]: https://taipangame.com/
  [3]: https://retrocomputing.stackexchange.com/q/28127/202
  [4]: https://gr33nonline.wordpress.com/2023/11/26/taipan-in-applesoft-basic/
