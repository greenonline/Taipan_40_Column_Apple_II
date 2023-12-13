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

The extraneous `V1` has *already* been removed from line 5040 (page 200)

```
5040 DATA V1 " : "
```

#### `CHR$(133)` - A hangover from the Tandy version

Line 150 (page 42) is given as 
```
150 FOR I = 0 TO 5: VTAB 5 + I:PRINT G$(I):VTAB 5 + I:HTAB 11:PRINT CHR$ (133);: Q=SG(I):GOSUB 1330:VTAB 5 + I:HTAB 26:PRINT CHR$ (133);: Q = GG(I):GOSUB 1330: NEXT I: INVERSE: PRINT A$: NORMAL: RETURN
```
However, `CHR$(133) is only a valid symbol on the TRS-80 (vertical bar). The `CHR$(133)` can be removed from the Applesoft version, as that character code prints nothing useful:
```
150 FOR I = 0 TO 5: VTAB 5 + I:PRINT G$(I):VTAB 5 + I:HTAB 11: Q=SG(I):GOSUB 1330:VTAB 5 + I:HTAB 26: Q = GG(I):GOSUB 1330: NEXT I: INVERSE: PRINT A$: NORMAL: RETURN
```
Or you could replace `CHR$(133)` with `CHR$(124)`, which is a thin vertical bar.

For more information, see [Looking for an accurate Apple II(e) character set - in particular, what is CHR$(133)?][4]

#### Missing space in goods table

The header for the goods table, is printed in line 141 (page 39)
```
141 VTAB 4: INVERSE:PRINT "GOODS    ABOARD SHIP    HONGKONG GODOWN":NORMAL
```
The book shows four space characters between `GOODS` and `ABOARD` and also between `SHIP` and `HONGKONG`, but this means that the inverse title bar is one character short, across the screen:

[![Port screen showing banner being one character too short][3]][3]

However, adding a space either before the `ABOARD` or between `HONG` and `KONG` (depending upon whether you think "Hongkong" is one word or two), fixes this issue, i.e.,
```
141 VTAB 4: INVERSE:PRINT "GOODS    ABOARD SHIP    HONG KONG GODOWN":NORMAL
```
#### Extraneous comma or semicolon?

In line 5350 (page 201), there is a combination of `,;`. However, surely the semicolon is not needed..?
```
5350 VTAB B+1: HTAB40-A:PRINT LEFT$ (CH$(B) ,A),;" ";
```
should be
```
5350 VTAB B+1: HTAB40-A:PRINT LEFT$ (CH$(B) ,A)," ";
```
### See also
- [Looking for an accurate Apple II(e) character set - in particular, what is CHR$(133)?][4]
- [Taipan in Applesoft BASIC][5]



  [1]: https://taipangame.com/pdf/TaipanAHistoricalAdventureForTheAppleComputerAppleIIEdition.pdf
  [2]: https://taipangame.com/
  [3]: https://i.stack.imgur.com/GPdtU.png
  [4]: https://retrocomputing.stackexchange.com/q/28127/202
  [5]: https://gr33nonline.wordpress.com/2023/11/26/taipan-in-applesoft-basic/
