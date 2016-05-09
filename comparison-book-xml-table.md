---
title: Comparison of XML structures for books
...

Comparison of XML structures for books
======================================

Version: 2016-05-09

There are books. Besides all the different ways of how people talk about
"knowledge production", the book has prevailed. Call it a collection of
articles or a container for text and media elements, people will still
call it a book. The content and structure of a book is generated and
stored in different ways. The below list is an attempt to compare
different XML concepts that try to define and describe a book.

This document is a work in progress, a research we are undertaking to
identify what would be the most "productive" way to add XML-export to
Booktype. Along the way of this research, it became clear that this
might be of general interest. Feel free to chip in with pull requests to
keep this up to date and extend it.

Links to explore
----------------

-   DocBook 5.1:  The Definitive Guide:
    [http://docbook.org/tdg51/en/html/docbook.html](http://docbook.org/tdg51/en/html/docbook.html)
-   HTMLBook. Unofficial Draft
    [http://oreillymedia.github.io/HTMLBook/](http://oreillymedia.github.io/HTMLBook/)
-   Open XML Paper Specification Standard ECMA-388
    [http://www.ecma-international.org/publications/standards/Ecma-388.htm](Open%20XML%20Paper%20Specification%20)
-   Book and Collection Tag Library version 3.0
    [http://dtd.nlm.nih.gov/book/tag-library/](Book%20and%20Collection%20Tag%20Libraryversion%203.0)
-   Booktype: [https://booktype.pro](https://booktype.pro)

XML elements and structure
--------------------------

### Paragraph formats

+-----------+-----------+-----------+-----------+-----------+-----------+-----------+-----------+
| \         | Normal    | Header    | Heading   | SubHeadin | SubSubHea | Pre-Forma | Quote     |
|           |           |           | (title)   | g         | ding      | ted       |           |
+-----------+-----------+-----------+-----------+-----------+-----------+-----------+-----------+
| In        | y         | n         | y         | y         | y         | y         | y         |
| Booktype? |           |           |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+-----------+-----------+
| DocBook   |     <form |     <arti | \         | [http://d | \         | \         | \         |
| 5.1       | alpara><t | cle xmlns |           | ocbook.or |           |           |           |
|           | itle>This | ='http:// |           | g/tdg51/e |           |           |           |
|           |  Paragrap | docbook.o |           | n/html/su |           |           |           |
|           | h Has a T | rg/ns/doc |           | btitle.ht |           |           |           |
|           | itle</tit | book'>    |           | ml](http: |           |           |           |
|           | le>       |     <titl |           | //docbook |           |           |           |
|           |     <para | e>Example |           | .org/tdg5 |           |           |           |
|           | >This is  |  title</t |           | 1/en/html |           |           |           |
|           | a test.   | itle>     |           | /subtitle |           |           |           |
|           | This is o |     <sect |           | .html)    |           |           |           |
|           | nly a tes | ion>      |           |           |           |           |           |
|           | t.  Had t |       <ti |           |           |           |           |           |
|           | his been  | tle>A Top |           |           |           |           |           |
|           | a real    |  Level Se |           |           |           |           |           |
|           |     examp | ction</ti |           |           |           |           |           |
|           | le, it wo | tle>      |           |           |           |           |           |
|           | uld have  |       <pa |           |           |           |           |           |
|           | made more | ra>Actual |           |           |           |           |           |
|           |  sense.   |  content. |           |           |           |           |           |
|           | Or less.  | </para>   |           |           |           |           |           |
|           |     </par |     </sec |           |           |           |           |           |
|           | a>        | tion>     |           |           |           |           |           |
|           |     </for |     </art |           |           |           |           |           |
|           | malpara>  | icle>     |           |           |           |           |           |
|           |           |           |           |           |           |           |           |
|           | [http://d | [http://d |           |           |           |           |           |
|           | ocbook.or | ocbook.or |           |           |           |           |           |
|           | g/tdg51/e | g/tdg51/e |           |           |           |           |           |
|           | n/html/fo | n/html/ti |           |           |           |           |           |
|           | rmalpara. | tle.html] |           |           |           |           |           |
|           | html](htt | (http://d |           |           |           |           |           |
|           | p://docbo | ocbook.or |           |           |           |           |           |
|           | ok.org/td | g/tdg51/e |           |           |           |           |           |
|           | g51/en/ht | n/html/ti |           |           |           |           |           |
|           | ml/formal | tle.html) |           |           |           |           |           |
|           | para.html |           |           |           |           |           |           |
|           | )\        |           |           |           |           |           |           |
|           |           |           |           |           |           |           |           |
|           | [http://d |           |           |           |           |           |           |
|           | ocbook.or |           |           |           |           |           |           |
|           | g/tdg51/e |           |           |           |           |           |           |
|           | n/html/pa |           |           |           |           |           |           |
|           | ra.html]( |           |           |           |           |           |           |
|           | http://do |           |           |           |           |           |           |
|           | cbook.org |           |           |           |           |           |           |
|           | /tdg51/en |           |           |           |           |           |           |
|           | /html/par |           |           |           |           |           |           |
|           | a.html)\  |           |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+-----------+-----------+
| HTML Book | ~~~~ {dat | \         | \         | \         | \         | \         | ~~~~ {dat |
|           | a-type="p | ~~~~ {dat |           |           |           |           | a-type="p |
|           | rogramlis | a-type="p |           |           |           |           | rogramlis |
|           | ting"}    | rogramlis |           |           |           |           | ting"}    |
|           | <p>This i | ting"}    |           |           |           |           | <blockquo |
|           | s a stand | <section  |           |           |           |           | te>       |
|           | ard parag | data-type |           |           |           |           |   <p>When |
|           | raph with | ="chapter |           |           |           |           |  in the c |
|           |  some <em | ">        |           |           |           |           | ourse of  |
|           | >emphasiz |   <header |           |           |           |           | human eve |
|           | ed text</ | >         |           |           |           |           | nts...</p |
|           | em></p>   |     <h1>C |           |           |           |           | >         |
|           | ~~~~      | hapter ti |           |           |           |           |   <p data |
|           |           | tle</h1>  |           |           |           |           | -type="at |
|           | [http://o |     <p da |           |           |           |           | tribution |
|           | reillymed | ta-type=" |           |           |           |           | ">U.S. De |
|           | ia.github | subtitle" |           |           |           |           | claration |
|           | .io/HTMLB | >Chapter  |           |           |           |           |  of Indep |
|           | ook/\#\_p | subtitle< |           |           |           |           | endence</ |
|           | aragraph] | /p>       |           |           |           |           | p>        |
|           | (http://o |   </heade |           |           |           |           | </blockqu |
|           | reillymed | r>        |           |           |           |           | ote>      |
|           | ia.github |   <!-- Ch |           |           |           |           | ~~~~      |
|           | .io/HTMLB | apter con |           |           |           |           |           |
|           | ook/#_par | tent here |           |           |           |           | [http://o |
|           | agraph)   | ... -->   |           |           |           |           | reillymed |
|           |           | </section |           |           |           |           | ia.github |
|           |           | >         |           |           |           |           | .io/HTMLB |
|           |           | ~~~~      |           |           |           |           | ook/\#\_b |
|           |           |           |           |           |           |           | lockquote |
|           |           | [http://o |           |           |           |           | ](http:// |
|           |           | reillymed |           |           |           |           | oreillyme |
|           |           | ia.github |           |           |           |           | dia.githu |
|           |           | .io/HTMLB |           |           |           |           | b.io/HTML |
|           |           | ook/\#hea |           |           |           |           | Book/#_bl |
|           |           | der\_bloc |           |           |           |           | ockquote) |
|           |           | k](http:/ |           |           |           |           | \         |
|           |           | /oreillym |           |           |           |           |           |
|           |           | edia.gith |           |           |           |           |           |
|           |           | ub.io/HTM |           |           |           |           |           |
|           |           | LBook/#he |           |           |           |           |           |
|           |           | ader_bloc |           |           |           |           |           |
|           |           | k)        |           |           |           |           |           |
|           |           | [http://o |           |           |           |           |           |
|           |           | reillymed |           |           |           |           |           |
|           |           | ia.github |           |           |           |           |           |
|           |           | .io/HTMLB |           |           |           |           |           |
|           |           | ook/\#\_h |           |           |           |           |           |
|           |           | eading\_e |           |           |           |           |           |
|           |           | lements]( |           |           |           |           |           |
|           |           | http://or |           |           |           |           |           |
|           |           | eillymedi |           |           |           |           |           |
|           |           | a.github. |           |           |           |           |           |
|           |           | io/HTMLBo |           |           |           |           |           |
|           |           | ok/#_head |           |           |           |           |           |
|           |           | ing_eleme |           |           |           |           |           |
|           |           | nts)\     |           |           |           |           |           |
|           |           |  \        |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+-----------+-----------+

### Alignment

  -------------- ------ ------- -------- -----------
  \              Left   Right   Center   Justified
                                         

  In Booktype?   y      y       y        y

  DocBook 5.1    \      \       \        \
                                         

  HTML Book\     \      \       \        \
                                         
  -------------- ------ ------- -------- -----------

### Font formatting

+------------+------------+------------+------------+------------+------------+------------+
| \          | Bold       | Italicise  | Underline  | Color      | Font-size  | Font-famil |
|            |            |            |            |            |            | y          |
+------------+------------+------------+------------+------------+------------+------------+
| In         | y          | y          | y          | y          | y          | y\         |
| Booktype?  |            |            |            |            |            |            |
+------------+------------+------------+------------+------------+------------+------------+
| XML        | \          | \          | \          | \          | \          | \          |
| Standard   |            |            |            |            |            |            |
+------------+------------+------------+------------+------------+------------+------------+
| DocBook    | \          | \          | \          | \          | \          | \          |
| 5.1        |            |            |            |            |            |            |
+------------+------------+------------+------------+------------+------------+------------+
| HTML Book  | ~~~~ {data | ~~~~ {data | ~~~~ {data | \          | \          | \          |
|            | -type="pro | -type="pro | -type="pro |            |            |            |
|            | gramlistin | gramlistin | gramlistin |            |            |            |
|            | g"}        | g"}        | g"}        |            |            |            |
|            | <p>I <stro | <p>I <em>l | <p>Use you |            |            |            |
|            | ng>love</s | ove</em> H | r own clas |            |            |            |
|            | trong> HTM | TML!</p>   | s attribut |            |            |            |
|            | L!</p>     | ~~~~       | es for cus |            |            |            |
|            | ~~~~       |            | tom stylin |            |            |            |
|            |            | [http://or | g for form |            |            |            |
|            | [http://or | eillymedia | atting lik |            |            |            |
|            | eillymedia | .github.io | e <span cl |            |            |            |
|            | .github.io | /HTMLBook/ | ass="under |            |            |            |
|            | /HTMLBook/ | \#\_emphas | line">unde |            |            |            |
|            | \#\_strong | is\_genera | rlined tex |            |            |            |
|            | \_generall | lly\_for\_ | t</span></ |            |            |            |
|            | y\_for\_bo | italic](ht | p>         |            |            |            |
|            | ld](http:/ | tp://oreil | ~~~~       |            |            |            |
|            | /oreillyme | lymedia.gi |            |            |            |            |
|            | dia.github | thub.io/HT | [http://or |            |            |            |
|            | .io/HTMLBo | MLBook/#_e | eillymedia |            |            |            |
|            | ok/#_stron | mphasis_ge | .github.io |            |            |            |
|            | g_generall | nerally_fo | /HTMLBook/ |            |            |            |
|            | y_for_bold | r_italic)  | \#\_genera |            |            |            |
|            | )          |            | l\_purpose |            |            |            |
|            |            |            | \_phrase\_ |            |            |            |
|            |            |            | markup\_fo |            |            |            |
|            |            |            | r\_other\_ |            |            |            |
|            |            |            | styling\_u |            |            |            |
|            |            |            | nderline\_ |            |            |            |
|            |            |            | strikethro |            |            |            |
|            |            |            | ugh\_etc]( |            |            |            |
|            |            |            | http://ore |            |            |            |
|            |            |            | illymedia. |            |            |            |
|            |            |            | github.io/ |            |            |            |
|            |            |            | HTMLBook/# |            |            |            |
|            |            |            | _general_p |            |            |            |
|            |            |            | urpose_phr |            |            |            |
|            |            |            | ase_markup |            |            |            |
|            |            |            | _for_other |            |            |            |
|            |            |            | _styling_u |            |            |            |
|            |            |            | nderline_s |            |            |            |
|            |            |            | trikethrou |            |            |            |
|            |            |            | gh_etc)    |            |            |            |
+------------+------------+------------+------------+------------+------------+------------+

### Other elements

+------------+------------+------------+------------+------------+------------+------------+
| \          | Links      | Unordered  | Ordered    | Right to   | Chapter    | Footnotes  |
|            | (anchor)   | (itemized) | list       | left text  | endnotes   |            |
|            |            | list       |            |            |            |            |
+------------+------------+------------+------------+------------+------------+------------+
| In         | y          | y          | y          | y\         | y          | n          |
| Booktype?  |            |            |            |            |            |            |
+------------+------------+------------+------------+------------+------------+------------+
| DocBook    |     <para> |     <itemi |     <order | \          | \          |     <para> |
| 5.1        | The anchor | zedlist ma | edlist num |            |            | An annual  |
|            |  element<a | rk='openci | eration="l |            |            | percentage |
|            | nchor xml: | rcle'>     | owerroman" |            |            |  rate (<ab |
|            | id="exampl |       <lis | >          |            |            | brev>APR</ |
|            | e.anchor.1 | titem>     |       <lis |            |            | abbrev>) o |
|            | "/> is emp |         <p | titem>     |            |            | f 13.9%<fo |
|            | ty and con | ara>TeX an |         <p |            |            | otnote>    |
|            | tributes   | d LaTeX    | ara>One</p |            |            |     <para> |
|            |     nothin |         </ | ara>       |            |            | The prime  |
|            | g to the f | para>      |       </li |            |            | rate, as p |
|            | low of the |       </li | stitem>    |            |            | ublished i |
|            |  content i | stitem>    |       <lis |            |            | n the <cit |
|            | n which it |       <lis | titem>     |            |            | etitle>Wal |
|            |  occurs.   | titem over |         <p |            |            | l Street   |
|            | It is only | ride='bull | ara>Two</p |            |            |     Journa |
|            |  useful    | et'>       | ara>       |            |            | l</citetit |
|            |     as a t |         <p |       </li |            |            | le> on the |
|            | arget.     | ara>Troff  | stitem>    |            |            |  first bus |
|            |     </para |         </ |       <lis |            |            | iness day  |
|            | >          | para>      | titem>     |            |            | of the mon |
|            |            |       </li |         <p |            |            | th,        |
|            | [http://do | stitem>    | ara>Three< |            |            |     plus 7 |
|            | cbook.org/ |       <lis | /para>     |            |            | .0%.       |
|            | tdg51/en/h | titem>     |       </li |            |            |     </para |
|            | tml/anchor |         <p | stitem>    |            |            | >          |
|            | .html](htt | ara>Lout   |       <lis |            |            |     </foot |
|            | p://docboo |         </ | titem>     |            |            | note>      |
|            | k.org/tdg5 | para>      |         <p |            |            |     will b |
|            | 1/en/html/ |       </li | ara>Four</ |            |            | e charged  |
|            | anchor.htm | stitem>    | para>      |            |            | on all bal |
|            | l)         |     </item |       </li |            |            | ances carr |
|            |            | izedlist>  | stitem>    |            |            | ied forwar |
|            |            |            |     </orde |            |            | d.         |
|            |            | [http://do | redlist>   |            |            |     </para |
|            |            | cbook.org/ |            |            |            | >          |
|            |            | tdg51/en/h | [http://do |            |            |            |
|            |            | tml/itemiz | cbook.org/ |            |            | [http://do |
|            |            | edlist.htm | tdg51/en/h |            |            | cbook.org/ |
|            |            | l](http:// | tml/ordere |            |            | tdg51/en/h |
|            |            | docbook.or | dlist.html |            |            | tml/footno |
|            |            | g/tdg51/en | ](http://d |            |            | te.html](h |
|            |            | /html/item | ocbook.org |            |            | ttp://docb |
|            |            | izedlist.h | /tdg51/en/ |            |            | ook.org/td |
|            |            | tml)       | html/order |            |            | g51/en/htm |
|            |            |            | edlist.htm |            |            | l/footnote |
|            |            |            | l)         |            |            | .html)\    |
|            |            |            |            |            |            |            |
|            |            |            |            |            |            | [http://do |
|            |            |            |            |            |            | cbook.org/ |
|            |            |            |            |            |            | tdg51/en/h |
|            |            |            |            |            |            | tml/footno |
|            |            |            |            |            |            | teref.html |
|            |            |            |            |            |            | ](http://d |
|            |            |            |            |            |            | ocbook.org |
|            |            |            |            |            |            | /tdg51/en/ |
|            |            |            |            |            |            | html/footn |
|            |            |            |            |            |            | oteref.htm |
|            |            |            |            |            |            | l)         |
+------------+------------+------------+------------+------------+------------+------------+
| HTML Book  | \          | ~~~~ {data | ~~~~ {data | \          | \          | ~~~~ {data |
|            |            | -type="pro | -type="pro |            |            | -type="pro |
|            |            | gramlistin | gramlistin |            |            | gramlistin |
|            |            | g"}        | g"}        |            |            | g"}        |
|            |            | <ul>       | <ol>       |            |            | <p>Five ou |
|            |            | <li>Red</l | <li>Step 1 |            |            | t of every |
|            |            | i>         | </li>      |            |            |  six peopl |
|            |            | <li>Orange | <li>       |            |            | e who try  |
|            |            | </li>      |   <p>Step  |            |            | AsciiDoc p |
|            |            | <!-- And s | 2</p>      |            |            | refer it t |
|            |            | o on -->   |   <p>Step  |            |            | o          |
|            |            | </ul>      | 2 continue |            |            | Markdown<s |
|            |            | ~~~~       | d</p>      |            |            | pan data-t |
|            |            |            | </li>      |            |            | ype="footn |
|            |            | [http://or | <!-- And s |            |            | ote">Total |
|            |            | eillymedia | o on -->   |            |            | ly made-up |
|            |            | .github.io | </ol>      |            |            |  statistic |
|            |            | /HTMLBook/ | ~~~~       |            |            | </span></p |
|            |            | \#\_itemiz |            |            |            | >          |
|            |            | ed\_lists] | [http://or |            |            | ~~~~       |
|            |            | (http://or | eillymedia |            |            |            |
|            |            | eillymedia | .github.io |            |            | [http://or |
|            |            | .github.io | /HTMLBook/ |            |            | eillymedia |
|            |            | /HTMLBook/ | \#\_ordere |            |            | .github.io |
|            |            | #_itemized | d\_lists]( |            |            | /HTMLBook/ |
|            |            | _lists)    | http://ore |            |            | \#\_footno |
|            |            |            | illymedia. |            |            | te\_endnot |
|            |            |            | github.io/ |            |            | e](http:// |
|            |            |            | HTMLBook/# |            |            | oreillymed |
|            |            |            | _ordered_l |            |            | ia.github. |
|            |            |            | ists)      |            |            | io/HTMLBoo |
|            |            |            |            |            |            | k/#_footno |
|            |            |            |            |            |            | te_endnote |
|            |            |            |            |            |            | )          |
+------------+------------+------------+------------+------------+------------+------------+

### Tables

+--------------------------------------+--------------------------------------+
| \                                    | Tables                               |
+--------------------------------------+--------------------------------------+
| In Booktype?                         | y                                    |
+--------------------------------------+--------------------------------------+
| DocBook 5.1                          |     <article xmlns='http://docbook.o |
|                                      | rg/ns/docbook'>                      |
|                                      |     <title>Example table</title>     |
|                                      |                                      |
|                                      |     <table xml:id="ex.htmltable">    |
|                                      |     <caption>Sample HTML Table</capt |
|                                      | ion>                                 |
|                                      |     <thead>                          |
|                                      |       <tr>                           |
|                                      |         <td>Head 1</td>              |
|                                      |         <td>Head 2</td>              |
|                                      |       </tr>                          |
|                                      |     </thead>                         |
|                                      |     <tbody>                          |
|                                      |       <tr>                           |
|                                      |         <td>Body 1</td>              |
|                                      |         <td>Body 2</td>              |
|                                      |       </tr>                          |
|                                      |     </tbody>                         |
|                                      |     </table>                         |
|                                      |                                      |
|                                      |     </article>                       |
|                                      |                                      |
|                                      | [http://docbook.org/tdg51/en/html/ht |
|                                      | ml.table.html](http://docbook.org/td |
|                                      | g51/en/html/html.table.html)\        |
+--------------------------------------+--------------------------------------+
| HTML Book                            | ~~~~ {data-type="programlisting"}    |
|                                      | <table>                              |
|                                      | <caption>State capitals</caption>    |
|                                      | <tr>                                 |
|                                      |   <th>State</th>                     |
|                                      |   <th>Capital</th>                   |
|                                      | </tr>                                |
|                                      | <tr>                                 |
|                                      |   <td>Massachusetts</td>             |
|                                      |   <td>Boston</td>                    |
|                                      | </tr>                                |
|                                      | <!-- And so on -->                   |
|                                      | </table>                             |
|                                      | ~~~~                                 |
|                                      |                                      |
|                                      | ~~~~ {data-type="programlisting"}    |
|                                      | <table>                              |
|                                      |   <thead>                            |
|                                      |     <tr>                             |
|                                      |       <th>First</th>                 |
|                                      |       <th>Middle Initial</th>        |
|                                      |       <th>Last</th>                  |
|                                      |     </tr>                            |
|                                      |   </thead>                           |
|                                      |   <tbody>                            |
|                                      |     <tr>                             |
|                                      |       <td>Alfred</td>                |
|                                      |       <td>E.</td>                    |
|                                      |       <td>Newman</td>                |
|                                      |     </tr>                            |
|                                      |     <!-- And so on -->               |
|                                      |   </tbody>                           |
|                                      | </table>                             |
|                                      | ~~~~                                 |
|                                      |                                      |
|                                      | [http://oreillymedia.github.io/HTMLB |
|                                      | ook/\#\_tables](http://oreillymedia. |
|                                      | github.io/HTMLBook/#_tables)         |
+--------------------------------------+--------------------------------------+

### Images / figures

+--------------------------------------+--------------------------------------+
| \                                    | Figures                              |
+--------------------------------------+--------------------------------------+
| In Booktype?                         | y                                    |
+--------------------------------------+--------------------------------------+
| DocBook 5.1                          |     <informalfigure>                 |
|                                      |     <mediaobject>                    |
|                                      |       <imageobject condition="print" |
|                                      | >                                    |
|                                      |         <info>                       |
|                                      |           <author>                   |
|                                      |             <personname>             |
|                                      |               <firstname>Norman</fir |
|                                      | stname>                              |
|                                      |               <surname>Walsh</surnam |
|                                      | e>                                   |
|                                      |             </personname>            |
|                                      |           </author>                  |
|                                      |           <pubdate>1998</pubdate>    |
|                                      |         </info>                      |
|                                      |                                      |
|                                      |         <imagedata fileref="figs/pri |
|                                      | nt/db5d_ref10.pdf" format="PDF" role |
|                                      | ="keep-together"/>                   |
|                                      |       </imageobject>                 |
|                                      |                                      |
|                                      |       <imageobject condition="web">  |
|                                      |         <imagedata fileref="figs/web |
|                                      | /db5d_ref10.png" format="PNG"/>      |
|                                      |       </imageobject>                 |
|                                      |                                      |
|                                      |       <textobject>                   |
|                                      |         <phrase>Wat Arun</phrase>    |
|                                      |       </textobject>                  |
|                                      |                                      |
|                                      |       <caption><para>Wat Arun, Templ |
|                                      | e of the Dawn, on the Chao Phraya    |
|                                      |       River in Bangkok, Thailand. In |
|                                      |  April 1998, Wat Arun was in the     |
|                                      |       midst of renovation.</para></c |
|                                      | aption>                              |
|                                      |     </mediaobject>                   |
|                                      |     </informalfigure>                |
|                                      |                                      |
|                                      | [http://docbook.org/tdg51/en/html/in |
|                                      | formalfigure.html](http://docbook.or |
|                                      | g/tdg51/en/html/informalfigure.html) |
|                                      | \                                    |
+--------------------------------------+--------------------------------------+
| HTML Book                            | ~~~~ {data-type="programlisting"}    |
|                                      | <figure>                             |
|                                      | <figcaption>Adorable cat</figcaption |
|                                      | >                                    |
|                                      | <img src="cute_kitty.gif" alt="Photo |
|                                      |  of an adorable cat"/>               |
|                                      | </figure>                            |
|                                      | ~~~~                                 |
|                                      |                                      |
|                                      | [http://oreillymedia.github.io/HTMLB |
|                                      | ook/\#\_figures](http://oreillymedia |
|                                      | .github.io/HTMLBook/#_figures)\      |
+--------------------------------------+--------------------------------------+

### Structure

+----------------+----------------+----------------+----------------+----------------+
| \              | Part           | Chapter        | SubChapter     | SubSubChapter  |
+----------------+----------------+----------------+----------------+----------------+
| In Booktype?   | y (called      | y              | n              | n\             |
|                | Section)       |                |                |                |
+----------------+----------------+----------------+----------------+----------------+
| DocBook 5.1    | [http://docboo | [http://docboo | \              | \              |
|                | k.org/tdg51/en | k.org/tdg51/en |                |                |
|                | /html/part.htm | /html/chapter. |                |                |
|                | l](http://docb | html](http://d |                |                |
|                | ook.org/tdg51/ | ocbook.org/tdg |                |                |
|                | en/html/part.h | 51/en/html/cha |                |                |
|                | tml)           | pter.html)     |                |                |
+----------------+----------------+----------------+----------------+----------------+
| HTML Book      | ~~~~ {data-typ | ~~~~ {data-typ | ~~~~ {data-typ | ~~~~ {data-typ |
|                | e="programlist | e="programlist | e="programlist | e="programlist |
|                | ing"}          | ing"}          | ing"}          | ing"}          |
|                | <div data-type | <section data- | <section data- | <section data- |
|                | ="part">       | type="chapter" | type="sect1">  | type="sect1">  |
|                |   <h1>Part One | >              |     <!-- Secti |   <h1>A-Head</ |
|                | : Introduction |   <!-- h1 used | on content her | h1>            |
|                |  to Backbone.j |  for all chapt | e... -->       |   <p>If you ht |
|                | s</h1>         | er titles -->  | </section>     | tpparty, you m |
|                |   <p>Part Intr |   <h1>Chapter  | ~~~~           | ust party hard |
|                | oduction...</p | Title</h1>     |                | </p>           |
|                | >              |   <p>Chapter c | [http://oreill |   <!-- Some mo |
|                |   <section dat | ontent</p>     | ymedia.github. | re paragraphs  |
|                | a-type="chapte |   <section dat | io/HTMLBook/\# | -->            |
|                | r">            | a-type="sect1" | \_sections](ht |   <section dat |
|                |     <!-- Chapt | >              | tp://oreillyme | a-type="sect2" |
|                | er content her |     <!-- Secti | dia.github.io/ | >              |
|                | e -->          | on content her | HTMLBook/#_sec |     <h2>B-Head |
|                |   </section>   | e... -->       | tions)\        | </h2>          |
|                | </div>         |   </section>   |                |     <p>What's  |
|                | ~~~~           | </section>     |                | the frequency, |
|                |                | ~~~~           |                |  Kenneth?</p>  |
|                | [http://oreill |                |                |     <!-- And s |
|                | ymedia.github. | [http://oreill |                | o on... -->    |
|                | io/HTMLBook/\# | ymedia.github. |                |   </section>   |
|                | \_part](http:/ | io/HTMLBook/\# |                | </section>     |
|                | /oreillymedia. | \_chapter](htt |                | ~~~~           |
|                | github.io/HTML | p://oreillymed |                |                |
|                | Book/#_part)   | ia.github.io/H |                | [http://oreill |
|                |                | TMLBook/#_chap |                | ymedia.github. |
|                |                | ter)           |                | io/HTMLBook/\# |
|                |                |                |                | \_sections](ht |
|                |                |                |                | tp://oreillyme |
|                |                |                |                | dia.github.io/ |
|                |                |                |                | HTMLBook/#_sec |
|                |                |                |                | tions)\        |
+----------------+----------------+----------------+----------------+----------------+
