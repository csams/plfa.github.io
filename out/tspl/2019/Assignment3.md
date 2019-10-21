---
src       : "courses/tspl/2019/Assignment3.lagda.md"
title     : "Assignment3: TSPL Assignment 3"
layout    : page
permalink : /TSPL/2019/Assignment3/
---

{% raw %}<pre class="Agda"><a id="112" class="Keyword">module</a> <a id="119" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}" class="Module">Assignment3</a> <a id="131" class="Keyword">where</a>
</pre>{% endraw %}
## YOUR NAME AND EMAIL GOES HERE

## Introduction

You must do _all_ the exercises labelled "(recommended)".

Exercises labelled "(stretch)" are there to provide an extra challenge.
You don't need to do all of these, but should attempt at least a few.

Exercises labelled "(practice)" are included for those who want extra practice.

Submit your homework using the "submit" command.
Please ensure your files execute correctly under Agda!


## Good Scholarly Practice.

Please remember the University requirement as
regards all assessed work. Details about this can be found at:

> [http://web.inf.ed.ac.uk/infweb/admin/policies/academic-misconduct](http://web.inf.ed.ac.uk/infweb/admin/policies/academic-misconduct)

Furthermore, you are required to take reasonable measures to protect
your assessed work from unauthorised access. For example, if you put
any such work on a public repository then you must set access
permissions appropriately (generally permitting access only to
yourself, or your group in the case of group practicals).


## Imports

{% raw %}<pre class="Agda"><a id="1198" class="Keyword">import</a> <a id="1205" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.html" class="Module">Relation.Binary.PropositionalEquality</a> <a id="1243" class="Symbol">as</a> <a id="1246" class="Module">Eq</a>
<a id="1249" class="Keyword">open</a> <a id="1254" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.html" class="Module">Eq</a> <a id="1257" class="Keyword">using</a> <a id="1263" class="Symbol">(</a><a id="1264" href="Agda.Builtin.Equality.html#125" class="Datatype Operator">_≡_</a><a id="1267" class="Symbol">;</a> <a id="1269" href="Agda.Builtin.Equality.html#182" class="InductiveConstructor">refl</a><a id="1273" class="Symbol">;</a> <a id="1275" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.Core.html#1090" class="Function">cong</a><a id="1279" class="Symbol">;</a> <a id="1281" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.Core.html#939" class="Function">sym</a><a id="1284" class="Symbol">)</a>
<a id="1286" class="Keyword">open</a> <a id="1291" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.Core.html#2499" class="Module">Eq.≡-Reasoning</a> <a id="1306" class="Keyword">using</a> <a id="1312" class="Symbol">(</a><a id="1313" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.Core.html#2597" class="Function Operator">begin_</a><a id="1319" class="Symbol">;</a> <a id="1321" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.Core.html#2655" class="Function Operator">_≡⟨⟩_</a><a id="1326" class="Symbol">;</a> <a id="1328" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.Core.html#2714" class="Function Operator">_≡⟨_⟩_</a><a id="1334" class="Symbol">;</a> <a id="1336" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Binary.PropositionalEquality.Core.html#2892" class="Function Operator">_∎</a><a id="1338" class="Symbol">)</a>
<a id="1340" class="Keyword">open</a> <a id="1345" class="Keyword">import</a> <a id="1352" href="https://agda.github.io/agda-stdlib/v1.1/Data.Bool.Base.html" class="Module">Data.Bool.Base</a> <a id="1367" class="Keyword">using</a> <a id="1373" class="Symbol">(</a><a id="1374" href="Agda.Builtin.Bool.html#135" class="Datatype">Bool</a><a id="1378" class="Symbol">;</a> <a id="1380" href="Agda.Builtin.Bool.html#160" class="InductiveConstructor">true</a><a id="1384" class="Symbol">;</a> <a id="1386" href="Agda.Builtin.Bool.html#154" class="InductiveConstructor">false</a><a id="1391" class="Symbol">;</a> <a id="1393" href="https://agda.github.io/agda-stdlib/v1.1/Data.Bool.Base.html#1480" class="Function">T</a><a id="1394" class="Symbol">;</a> <a id="1396" href="https://agda.github.io/agda-stdlib/v1.1/Data.Bool.Base.html#1015" class="Function Operator">_∧_</a><a id="1399" class="Symbol">;</a> <a id="1401" href="https://agda.github.io/agda-stdlib/v1.1/Data.Bool.Base.html#1073" class="Function Operator">_∨_</a><a id="1404" class="Symbol">;</a> <a id="1406" href="https://agda.github.io/agda-stdlib/v1.1/Data.Bool.Base.html#961" class="Function">not</a><a id="1409" class="Symbol">)</a>
<a id="1411" class="Keyword">open</a> <a id="1416" class="Keyword">import</a> <a id="1423" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.html" class="Module">Data.Nat</a> <a id="1432" class="Keyword">using</a> <a id="1438" class="Symbol">(</a><a id="1439" href="Agda.Builtin.Nat.html#165" class="Datatype">ℕ</a><a id="1440" class="Symbol">;</a> <a id="1442" href="Agda.Builtin.Nat.html#183" class="InductiveConstructor">zero</a><a id="1446" class="Symbol">;</a> <a id="1448" href="Agda.Builtin.Nat.html#196" class="InductiveConstructor">suc</a><a id="1451" class="Symbol">;</a> <a id="1453" href="Agda.Builtin.Nat.html#298" class="Primitive Operator">_+_</a><a id="1456" class="Symbol">;</a> <a id="1458" href="Agda.Builtin.Nat.html#501" class="Primitive Operator">_*_</a><a id="1461" class="Symbol">;</a> <a id="1463" href="Agda.Builtin.Nat.html#388" class="Primitive Operator">_∸_</a><a id="1466" class="Symbol">;</a> <a id="1468" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Base.html#895" class="Datatype Operator">_≤_</a><a id="1471" class="Symbol">;</a> <a id="1473" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Base.html#960" class="InductiveConstructor">s≤s</a><a id="1476" class="Symbol">;</a> <a id="1478" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Base.html#918" class="InductiveConstructor">z≤n</a><a id="1481" class="Symbol">)</a>
<a id="1483" class="Keyword">open</a> <a id="1488" class="Keyword">import</a> <a id="1495" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Properties.html" class="Module">Data.Nat.Properties</a> <a id="1515" class="Keyword">using</a>
  <a id="1523" class="Symbol">(</a><a id="1524" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Properties.html#11578" class="Function">+-assoc</a><a id="1531" class="Symbol">;</a> <a id="1533" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Properties.html#11679" class="Function">+-identityˡ</a><a id="1544" class="Symbol">;</a> <a id="1546" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Properties.html#11734" class="Function">+-identityʳ</a><a id="1557" class="Symbol">;</a> <a id="1559" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Properties.html#18464" class="Function">*-assoc</a><a id="1566" class="Symbol">;</a> <a id="1568" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Properties.html#17362" class="Function">*-identityˡ</a><a id="1579" class="Symbol">;</a> <a id="1581" href="https://agda.github.io/agda-stdlib/v1.1/Data.Nat.Properties.html#17426" class="Function">*-identityʳ</a><a id="1592" class="Symbol">)</a>
<a id="1594" class="Keyword">open</a> <a id="1599" class="Keyword">import</a> <a id="1606" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Nullary.html" class="Module">Relation.Nullary</a> <a id="1623" class="Keyword">using</a> <a id="1629" class="Symbol">(</a><a id="1630" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Nullary.html#535" class="Function Operator">¬_</a><a id="1632" class="Symbol">;</a> <a id="1634" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Nullary.html#605" class="Datatype">Dec</a><a id="1637" class="Symbol">;</a> <a id="1639" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Nullary.html#641" class="InductiveConstructor">yes</a><a id="1642" class="Symbol">;</a> <a id="1644" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Nullary.html#668" class="InductiveConstructor">no</a><a id="1646" class="Symbol">)</a>
<a id="1648" class="Keyword">open</a> <a id="1653" class="Keyword">import</a> <a id="1660" href="https://agda.github.io/agda-stdlib/v1.1/Data.Product.html" class="Module">Data.Product</a> <a id="1673" class="Keyword">using</a> <a id="1679" class="Symbol">(</a><a id="1680" href="https://agda.github.io/agda-stdlib/v1.1/Data.Product.html#1162" class="Function Operator">_×_</a><a id="1683" class="Symbol">;</a> <a id="1685" href="https://agda.github.io/agda-stdlib/v1.1/Data.Product.html#1364" class="Function">∃</a><a id="1686" class="Symbol">;</a> <a id="1688" href="https://agda.github.io/agda-stdlib/v1.1/Data.Product.html#1783" class="Function">∃-syntax</a><a id="1696" class="Symbol">)</a> <a id="1698" class="Keyword">renaming</a> <a id="1707" class="Symbol">(</a><a id="1708" href="Agda.Builtin.Sigma.html#209" class="InductiveConstructor Operator">_,_</a> <a id="1712" class="Symbol">to</a> <a id="1715" href="Agda.Builtin.Sigma.html#209" class="InductiveConstructor Operator">⟨_,_⟩</a><a id="1720" class="Symbol">)</a>
<a id="1722" class="Keyword">open</a> <a id="1727" class="Keyword">import</a> <a id="1734" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html" class="Module">Data.Empty</a> <a id="1745" class="Keyword">using</a> <a id="1751" class="Symbol">(</a><a id="1752" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#279" class="Datatype">⊥</a><a id="1753" class="Symbol">;</a> <a id="1755" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#294" class="Function">⊥-elim</a><a id="1761" class="Symbol">)</a>
<a id="1763" class="Keyword">open</a> <a id="1768" class="Keyword">import</a> <a id="1775" href="https://agda.github.io/agda-stdlib/v1.1/Function.html" class="Module">Function</a> <a id="1784" class="Keyword">using</a> <a id="1790" class="Symbol">(</a><a id="1791" href="https://agda.github.io/agda-stdlib/v1.1/Function.html#1099" class="Function Operator">_∘_</a><a id="1794" class="Symbol">)</a>
<a id="1796" class="Keyword">open</a> <a id="1801" class="Keyword">import</a> <a id="1808" href="https://agda.github.io/agda-stdlib/v1.1/Algebra.Structures.html" class="Module">Algebra.Structures</a> <a id="1827" class="Keyword">using</a> <a id="1833" class="Symbol">(</a><a id="1834" href="https://agda.github.io/agda-stdlib/v1.1/Algebra.Structures.html#2215" class="Record">IsMonoid</a><a id="1842" class="Symbol">)</a>
<a id="1844" class="Keyword">open</a> <a id="1849" class="Keyword">import</a> <a id="1856" href="https://agda.github.io/agda-stdlib/v1.1/Level.html" class="Module">Level</a> <a id="1862" class="Keyword">using</a> <a id="1868" class="Symbol">(</a><a id="1869" href="Agda.Primitive.html#408" class="Postulate">Level</a><a id="1874" class="Symbol">)</a>
<a id="1876" class="Keyword">open</a> <a id="1881" class="Keyword">import</a> <a id="1888" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Unary.html" class="Module">Relation.Unary</a> <a id="1903" class="Keyword">using</a> <a id="1909" class="Symbol">(</a><a id="1910" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Unary.html#3474" class="Function">Decidable</a><a id="1919" class="Symbol">)</a>
<a id="1921" class="Keyword">open</a> <a id="1926" class="Keyword">import</a> <a id="1933" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Relations.md %}{% raw %}" class="Module">plfa.part1.Relations</a> <a id="1954" class="Keyword">using</a> <a id="1960" class="Symbol">(</a><a id="1961" href="plfa.part1.Relations.html#18383" class="Datatype Operator">_&lt;_</a><a id="1964" class="Symbol">;</a> <a id="1966" href="plfa.part1.Relations.html#18410" class="InductiveConstructor">z&lt;s</a><a id="1969" class="Symbol">;</a> <a id="1971" href="plfa.part1.Relations.html#18467" class="InductiveConstructor">s&lt;s</a><a id="1974" class="Symbol">)</a>
<a id="1976" class="Keyword">open</a> <a id="1981" class="Keyword">import</a> <a id="1988" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Isomorphism.md %}{% raw %}" class="Module">plfa.part1.Isomorphism</a> <a id="2011" class="Keyword">using</a> <a id="2017" class="Symbol">(</a><a id="2018" href="plfa.part1.Isomorphism.html#4365" class="Record Operator">_≃_</a><a id="2021" class="Symbol">;</a> <a id="2023" href="plfa.part1.Isomorphism.html#7012" class="Function">≃-sym</a><a id="2028" class="Symbol">;</a> <a id="2030" href="plfa.part1.Isomorphism.html#7337" class="Function">≃-trans</a><a id="2037" class="Symbol">;</a> <a id="2039" href="plfa.part1.Isomorphism.html#9186" class="Record Operator">_≲_</a><a id="2042" class="Symbol">;</a> <a id="2044" href="plfa.part1.Isomorphism.html#2684" class="Postulate">extensionality</a><a id="2058" class="Symbol">)</a>
<a id="2060" class="Keyword">open</a> <a id="2065" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Isomorphism.md %}{% raw %}#8421" class="Module">plfa.part1.Isomorphism.≃-Reasoning</a>
<a id="2100" class="Keyword">open</a> <a id="2105" class="Keyword">import</a> <a id="2112" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}" class="Module">plfa.part1.Lists</a> <a id="2129" class="Keyword">using</a> <a id="2135" class="Symbol">(</a><a id="2136" href="plfa.part1.Lists.html#1067" class="Datatype">List</a><a id="2140" class="Symbol">;</a> <a id="2142" href="plfa.part1.Lists.html#1096" class="InductiveConstructor">[]</a><a id="2144" class="Symbol">;</a> <a id="2146" href="plfa.part1.Lists.html#1111" class="InductiveConstructor Operator">_∷_</a><a id="2149" class="Symbol">;</a> <a id="2151" href="plfa.part1.Lists.html#2827" class="Operator">[_]</a><a id="2154" class="Symbol">;</a> <a id="2156" href="plfa.part1.Lists.html#2850" class="Operator">[_,_]</a><a id="2161" class="Symbol">;</a> <a id="2163" href="plfa.part1.Lists.html#2881" class="Operator">[_,_,_]</a><a id="2170" class="Symbol">;</a> <a id="2172" href="plfa.part1.Lists.html#2920" class="Operator">[_,_,_,_]</a><a id="2181" class="Symbol">;</a>
  <a id="2185" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#3467" class="Function Operator">_++_</a><a id="2189" class="Symbol">;</a> <a id="2191" href="plfa.part1.Lists.html#8321" class="Function">reverse</a><a id="2198" class="Symbol">;</a> <a id="2200" href="plfa.part1.Lists.html#12867" class="Function">map</a><a id="2203" class="Symbol">;</a> <a id="2205" href="plfa.part1.Lists.html#15293" class="Function">foldr</a><a id="2210" class="Symbol">;</a> <a id="2212" href="plfa.part1.Lists.html#16256" class="Function">sum</a><a id="2215" class="Symbol">;</a> <a id="2217" href="plfa.part1.Lists.html#21536" class="Datatype">All</a><a id="2220" class="Symbol">;</a> <a id="2222" href="plfa.part1.Lists.html#22989" class="Datatype">Any</a><a id="2225" class="Symbol">;</a> <a id="2227" href="plfa.part1.Lists.html#23040" class="InductiveConstructor">here</a><a id="2231" class="Symbol">;</a> <a id="2233" href="plfa.part1.Lists.html#23097" class="InductiveConstructor">there</a><a id="2238" class="Symbol">;</a> <a id="2240" href="plfa.part1.Lists.html#23411" class="Function Operator">_∈_</a><a id="2243" class="Symbol">)</a>
<a id="2245" class="Keyword">open</a> <a id="2250" class="Keyword">import</a> <a id="2257" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}" class="Module">plfa.part2.Lambda</a> <a id="2275" class="Keyword">hiding</a> <a id="2282" class="Symbol">(</a><a id="2283" href="plfa.part2.Lambda.html#7383" class="Function Operator">ƛ′_⇒_</a><a id="2288" class="Symbol">;</a> <a id="2290" href="plfa.part2.Lambda.html#7504" class="Function Operator">case′_[zero⇒_|suc_⇒_]</a><a id="2311" class="Symbol">;</a> <a id="2313" href="plfa.part2.Lambda.html#7718" class="Function Operator">μ′_⇒_</a><a id="2318" class="Symbol">;</a> <a id="2320" href="plfa.part2.Lambda.html#8468" class="Function">plus′</a><a id="2325" class="Symbol">)</a>
<a id="2327" class="Keyword">open</a> <a id="2332" class="Keyword">import</a> <a id="2339" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Properties.md %}{% raw %}" class="Module">plfa.part2.Properties</a> <a id="2361" class="Keyword">hiding</a> <a id="2368" class="Symbol">(</a><a id="2369" href="plfa.part2.Properties.html#11767" class="Postulate">value?</a><a id="2375" class="Symbol">;</a> <a id="2377" href="plfa.part2.Properties.html#41613" class="Postulate">unstuck</a><a id="2384" class="Symbol">;</a> <a id="2386" href="plfa.part2.Properties.html#41813" class="Postulate">preserves</a><a id="2395" class="Symbol">;</a> <a id="2397" href="plfa.part2.Properties.html#42050" class="Postulate">wttdgs</a><a id="2403" class="Symbol">)</a>
</pre>{% endraw %}

## Lists

#### Exercise `reverse-++-distrib` (recommended)

Show that the reverse of one list appended to another is the
reverse of the second appended to the reverse of the first:

    reverse (xs ++ ys) ≡ reverse ys ++ reverse xs


#### Exercise `reverse-involutive` (recommended)

A function is an _involution_ if when applied twice it acts
as the identity function.  Show that reverse is an involution:

    reverse (reverse xs) ≡ xs


#### Exercise `map-compose` (practice)

Prove that the map of a composition is equal to the composition of two maps:

    map (g ∘ f) ≡ map g ∘ map f

The last step of the proof requires extensionality.

#### Exercise `map-++-distribute` (practice)

Prove the following relationship between map and append:

   map f (xs ++ ys) ≡ map f xs ++ map f ys

#### Exercise `map-Tree` (practice)

Define a type of trees with leaves of type `A` and internal
nodes of type `B`:
{% raw %}<pre class="Agda"><a id="3323" class="Keyword">data</a> <a id="Tree"></a><a id="3328" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#3328" class="Datatype">Tree</a> <a id="3333" class="Symbol">(</a><a id="3334" href="Assignment3.html#3334" class="Bound">A</a> <a id="3336" href="Assignment3.html#3336" class="Bound">B</a> <a id="3338" class="Symbol">:</a> <a id="3340" class="PrimitiveType">Set</a><a id="3343" class="Symbol">)</a> <a id="3345" class="Symbol">:</a> <a id="3347" class="PrimitiveType">Set</a> <a id="3351" class="Keyword">where</a>
  <a id="Tree.leaf"></a><a id="3359" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#3359" class="InductiveConstructor">leaf</a> <a id="3364" class="Symbol">:</a> <a id="3366" href="Assignment3.html#3334" class="Bound">A</a> <a id="3368" class="Symbol">→</a> <a id="3370" href="Assignment3.html#3328" class="Datatype">Tree</a> <a id="3375" href="Assignment3.html#3334" class="Bound">A</a> <a id="3377" href="Assignment3.html#3336" class="Bound">B</a>
  <a id="Tree.node"></a><a id="3381" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#3381" class="InductiveConstructor">node</a> <a id="3386" class="Symbol">:</a> <a id="3388" href="Assignment3.html#3328" class="Datatype">Tree</a> <a id="3393" href="Assignment3.html#3334" class="Bound">A</a> <a id="3395" href="Assignment3.html#3336" class="Bound">B</a> <a id="3397" class="Symbol">→</a> <a id="3399" href="Assignment3.html#3336" class="Bound">B</a> <a id="3401" class="Symbol">→</a> <a id="3403" href="Assignment3.html#3328" class="Datatype">Tree</a> <a id="3408" href="Assignment3.html#3334" class="Bound">A</a> <a id="3410" href="Assignment3.html#3336" class="Bound">B</a> <a id="3412" class="Symbol">→</a> <a id="3414" href="Assignment3.html#3328" class="Datatype">Tree</a> <a id="3419" href="Assignment3.html#3334" class="Bound">A</a> <a id="3421" href="Assignment3.html#3336" class="Bound">B</a>
</pre>{% endraw %}Define a suitable map operator over trees:
{% raw %}<pre class="Agda"><a id="3474" class="Keyword">postulate</a>
  <a id="map-Tree"></a><a id="3486" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#3486" class="Postulate">map-Tree</a> <a id="3495" class="Symbol">:</a> <a id="3497" class="Symbol">∀</a> <a id="3499" class="Symbol">{</a><a id="3500" href="Assignment3.html#3500" class="Bound">A</a> <a id="3502" href="Assignment3.html#3502" class="Bound">B</a> <a id="3504" href="Assignment3.html#3504" class="Bound">C</a> <a id="3506" href="Assignment3.html#3506" class="Bound">D</a> <a id="3508" class="Symbol">:</a> <a id="3510" class="PrimitiveType">Set</a><a id="3513" class="Symbol">}</a>
    <a id="3519" class="Symbol">→</a> <a id="3521" class="Symbol">(</a><a id="3522" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#3500" class="Bound">A</a> <a id="3524" class="Symbol">→</a> <a id="3526" href="Assignment3.html#3504" class="Bound">C</a><a id="3527" class="Symbol">)</a> <a id="3529" class="Symbol">→</a> <a id="3531" class="Symbol">(</a><a id="3532" href="Assignment3.html#3502" class="Bound">B</a> <a id="3534" class="Symbol">→</a> <a id="3536" href="Assignment3.html#3506" class="Bound">D</a><a id="3537" class="Symbol">)</a> <a id="3539" class="Symbol">→</a> <a id="3541" href="Assignment3.html#3328" class="Datatype">Tree</a> <a id="3546" href="Assignment3.html#3500" class="Bound">A</a> <a id="3548" href="Assignment3.html#3502" class="Bound">B</a> <a id="3550" class="Symbol">→</a> <a id="3552" href="Assignment3.html#3328" class="Datatype">Tree</a> <a id="3557" href="Assignment3.html#3504" class="Bound">C</a> <a id="3559" href="Assignment3.html#3506" class="Bound">D</a>
</pre>{% endraw %}

#### Exercise `product` (recommended)

Use fold to define a function to find the product of a list of numbers.
For example:

    product [ 1 , 2 , 3 , 4 ] ≡ 24

{% raw %}<pre class="Agda"><a id="3732" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `foldr-++` (recommended)

Show that fold and append are related as follows:
{% raw %}<pre class="Agda"><a id="3854" class="Keyword">postulate</a>
  <a id="foldr-++"></a><a id="3866" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#3866" class="Postulate">foldr-++</a> <a id="3875" class="Symbol">:</a> <a id="3877" class="Symbol">∀</a> <a id="3879" class="Symbol">{</a><a id="3880" href="Assignment3.html#3880" class="Bound">A</a> <a id="3882" href="Assignment3.html#3882" class="Bound">B</a> <a id="3884" class="Symbol">:</a> <a id="3886" class="PrimitiveType">Set</a><a id="3889" class="Symbol">}</a> <a id="3891" class="Symbol">(</a><a id="3892" href="Assignment3.html#3892" class="Bound Operator">_⊗_</a> <a id="3896" class="Symbol">:</a> <a id="3898" href="Assignment3.html#3880" class="Bound">A</a> <a id="3900" class="Symbol">→</a> <a id="3902" href="Assignment3.html#3882" class="Bound">B</a> <a id="3904" class="Symbol">→</a> <a id="3906" href="Assignment3.html#3882" class="Bound">B</a><a id="3907" class="Symbol">)</a> <a id="3909" class="Symbol">(</a><a id="3910" href="Assignment3.html#3910" class="Bound">e</a> <a id="3912" class="Symbol">:</a> <a id="3914" href="Assignment3.html#3882" class="Bound">B</a><a id="3915" class="Symbol">)</a> <a id="3917" class="Symbol">(</a><a id="3918" href="Assignment3.html#3918" class="Bound">xs</a> <a id="3921" href="Assignment3.html#3921" class="Bound">ys</a> <a id="3924" class="Symbol">:</a> <a id="3926" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#1067" class="Datatype">List</a> <a id="3931" href="Assignment3.html#3880" class="Bound">A</a><a id="3932" class="Symbol">)</a> <a id="3934" class="Symbol">→</a>
    <a id="3940" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#15293" class="Function">foldr</a> <a id="3946" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#3892" class="Bound Operator">_⊗_</a> <a id="3950" href="Assignment3.html#3910" class="Bound">e</a> <a id="3952" class="Symbol">(</a><a id="3953" href="Assignment3.html#3918" class="Bound">xs</a> <a id="3956" href="plfa.part1.Lists.html#3467" class="Function Operator">++</a> <a id="3959" href="Assignment3.html#3921" class="Bound">ys</a><a id="3961" class="Symbol">)</a> <a id="3963" href="Agda.Builtin.Equality.html#125" class="Datatype Operator">≡</a> <a id="3965" href="plfa.part1.Lists.html#15293" class="Function">foldr</a> <a id="3971" href="Assignment3.html#3892" class="Bound Operator">_⊗_</a> <a id="3975" class="Symbol">(</a><a id="3976" href="plfa.part1.Lists.html#15293" class="Function">foldr</a> <a id="3982" href="Assignment3.html#3892" class="Bound Operator">_⊗_</a> <a id="3986" href="Assignment3.html#3910" class="Bound">e</a> <a id="3988" href="Assignment3.html#3921" class="Bound">ys</a><a id="3990" class="Symbol">)</a> <a id="3992" href="Assignment3.html#3918" class="Bound">xs</a>
</pre>{% endraw %}

#### Exercise `map-is-foldr` (practice)

Show that map can be defined using fold:
{% raw %}<pre class="Agda"><a id="4087" class="Keyword">postulate</a>
  <a id="map-is-foldr"></a><a id="4099" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4099" class="Postulate">map-is-foldr</a> <a id="4112" class="Symbol">:</a> <a id="4114" class="Symbol">∀</a> <a id="4116" class="Symbol">{</a><a id="4117" href="Assignment3.html#4117" class="Bound">A</a> <a id="4119" href="Assignment3.html#4119" class="Bound">B</a> <a id="4121" class="Symbol">:</a> <a id="4123" class="PrimitiveType">Set</a><a id="4126" class="Symbol">}</a> <a id="4128" class="Symbol">{</a><a id="4129" href="Assignment3.html#4129" class="Bound">f</a> <a id="4131" class="Symbol">:</a> <a id="4133" href="Assignment3.html#4117" class="Bound">A</a> <a id="4135" class="Symbol">→</a> <a id="4137" href="Assignment3.html#4119" class="Bound">B</a><a id="4138" class="Symbol">}</a> <a id="4140" class="Symbol">→</a>
    <a id="4146" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#12867" class="Function">map</a> <a id="4150" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4129" class="Bound">f</a> <a id="4152" href="Agda.Builtin.Equality.html#125" class="Datatype Operator">≡</a> <a id="4154" href="plfa.part1.Lists.html#15293" class="Function">foldr</a> <a id="4160" class="Symbol">(λ</a> <a id="4163" href="Assignment3.html#4163" class="Bound">x</a> <a id="4165" href="Assignment3.html#4165" class="Bound">xs</a> <a id="4168" class="Symbol">→</a> <a id="4170" href="Assignment3.html#4129" class="Bound">f</a> <a id="4172" href="Assignment3.html#4163" class="Bound">x</a> <a id="4174" href="plfa.part1.Lists.html#1111" class="InductiveConstructor Operator">∷</a> <a id="4176" href="Assignment3.html#4165" class="Bound">xs</a><a id="4178" class="Symbol">)</a> <a id="4180" href="plfa.part1.Lists.html#1096" class="InductiveConstructor">[]</a>
</pre>{% endraw %}This requires extensionality.

#### Exercise `fold-Tree` (practice)

Define a suitable fold function for the type of trees given earlier:
{% raw %}<pre class="Agda"><a id="4329" class="Keyword">postulate</a>
  <a id="fold-Tree"></a><a id="4341" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4341" class="Postulate">fold-Tree</a> <a id="4351" class="Symbol">:</a> <a id="4353" class="Symbol">∀</a> <a id="4355" class="Symbol">{</a><a id="4356" href="Assignment3.html#4356" class="Bound">A</a> <a id="4358" href="Assignment3.html#4358" class="Bound">B</a> <a id="4360" href="Assignment3.html#4360" class="Bound">C</a> <a id="4362" class="Symbol">:</a> <a id="4364" class="PrimitiveType">Set</a><a id="4367" class="Symbol">}</a>
    <a id="4373" class="Symbol">→</a> <a id="4375" class="Symbol">(</a><a id="4376" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4356" class="Bound">A</a> <a id="4378" class="Symbol">→</a> <a id="4380" href="Assignment3.html#4360" class="Bound">C</a><a id="4381" class="Symbol">)</a> <a id="4383" class="Symbol">→</a> <a id="4385" class="Symbol">(</a><a id="4386" href="Assignment3.html#4360" class="Bound">C</a> <a id="4388" class="Symbol">→</a> <a id="4390" href="Assignment3.html#4358" class="Bound">B</a> <a id="4392" class="Symbol">→</a> <a id="4394" href="Assignment3.html#4360" class="Bound">C</a> <a id="4396" class="Symbol">→</a> <a id="4398" href="Assignment3.html#4360" class="Bound">C</a><a id="4399" class="Symbol">)</a> <a id="4401" class="Symbol">→</a> <a id="4403" href="Assignment3.html#3328" class="Datatype">Tree</a> <a id="4408" href="Assignment3.html#4356" class="Bound">A</a> <a id="4410" href="Assignment3.html#4358" class="Bound">B</a> <a id="4412" class="Symbol">→</a> <a id="4414" href="Assignment3.html#4360" class="Bound">C</a>
</pre>{% endraw %}
{% raw %}<pre class="Agda"><a id="4425" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `map-is-fold-Tree` (practice)

Demonstrate an analogue of `map-is-foldr` for the type of trees.

{% raw %}<pre class="Agda"><a id="4568" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `sum-downFrom` (stretch)

Define a function that counts down as follows:
{% raw %}<pre class="Agda"><a id="downFrom"></a><a id="4687" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4687" class="Function">downFrom</a> <a id="4696" class="Symbol">:</a> <a id="4698" href="Agda.Builtin.Nat.html#165" class="Datatype">ℕ</a> <a id="4700" class="Symbol">→</a> <a id="4702" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#1067" class="Datatype">List</a> <a id="4707" href="Agda.Builtin.Nat.html#165" class="Datatype">ℕ</a>
<a id="4709" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4687" class="Function">downFrom</a> <a id="4718" href="Agda.Builtin.Nat.html#183" class="InductiveConstructor">zero</a>     <a id="4727" class="Symbol">=</a>  <a id="4730" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#1096" class="InductiveConstructor">[]</a>
<a id="4733" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4687" class="Function">downFrom</a> <a id="4742" class="Symbol">(</a><a id="4743" href="Agda.Builtin.Nat.html#196" class="InductiveConstructor">suc</a> <a id="4747" href="Assignment3.html#4747" class="Bound">n</a><a id="4748" class="Symbol">)</a>  <a id="4751" class="Symbol">=</a>  <a id="4754" href="Assignment3.html#4747" class="Bound">n</a> <a id="4756" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#1111" class="InductiveConstructor Operator">∷</a> <a id="4758" href="Assignment3.html#4687" class="Function">downFrom</a> <a id="4767" href="Assignment3.html#4747" class="Bound">n</a>
</pre>{% endraw %}For example:
{% raw %}<pre class="Agda"><a id="4790" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4790" class="Function">_</a> <a id="4792" class="Symbol">:</a> <a id="4794" href="Assignment3.html#4687" class="Function">downFrom</a> <a id="4803" class="Number">3</a> <a id="4805" href="Agda.Builtin.Equality.html#125" class="Datatype Operator">≡</a> <a id="4807" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#2881" class="InductiveConstructor Operator">[</a> <a id="4809" class="Number">2</a> <a id="4811" href="plfa.part1.Lists.html#2881" class="InductiveConstructor Operator">,</a> <a id="4813" class="Number">1</a> <a id="4815" href="plfa.part1.Lists.html#2881" class="InductiveConstructor Operator">,</a> <a id="4817" class="Number">0</a> <a id="4819" href="plfa.part1.Lists.html#2881" class="InductiveConstructor Operator">]</a>
<a id="4821" class="Symbol">_</a> <a id="4823" class="Symbol">=</a> <a id="4825" href="Agda.Builtin.Equality.html#182" class="InductiveConstructor">refl</a>
</pre>{% endraw %}Prove that the sum of the numbers `(n - 1) + ⋯ + 0` is
equal to `n * (n ∸ 1) / 2`:
{% raw %}<pre class="Agda"><a id="4921" class="Keyword">postulate</a>
  <a id="sum-downFrom"></a><a id="4933" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4933" class="Postulate">sum-downFrom</a> <a id="4946" class="Symbol">:</a> <a id="4948" class="Symbol">∀</a> <a id="4950" class="Symbol">(</a><a id="4951" href="Assignment3.html#4951" class="Bound">n</a> <a id="4953" class="Symbol">:</a> <a id="4955" href="Agda.Builtin.Nat.html#165" class="Datatype">ℕ</a><a id="4956" class="Symbol">)</a>
    <a id="4962" class="Symbol">→</a> <a id="4964" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#16256" class="Function">sum</a> <a id="4968" class="Symbol">(</a><a id="4969" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#4687" class="Function">downFrom</a> <a id="4978" href="Assignment3.html#4951" class="Bound">n</a><a id="4979" class="Symbol">)</a> <a id="4981" href="Agda.Builtin.Nat.html#501" class="Primitive Operator">*</a> <a id="4983" class="Number">2</a> <a id="4985" href="Agda.Builtin.Equality.html#125" class="Datatype Operator">≡</a> <a id="4987" href="Assignment3.html#4951" class="Bound">n</a> <a id="4989" href="Agda.Builtin.Nat.html#501" class="Primitive Operator">*</a> <a id="4991" class="Symbol">(</a><a id="4992" href="Assignment3.html#4951" class="Bound">n</a> <a id="4994" href="Agda.Builtin.Nat.html#388" class="Primitive Operator">∸</a> <a id="4996" class="Number">1</a><a id="4997" class="Symbol">)</a>
</pre>{% endraw %}

#### Exercise `foldl` (practice)

Define a function `foldl` which is analogous to `foldr`, but where
operations associate to the left rather than the right.  For example:

    foldr _⊗_ e [ x , y , z ]  =  x ⊗ (y ⊗ (z ⊗ e))
    foldl _⊗_ e [ x , y , z ]  =  ((e ⊗ x) ⊗ y) ⊗ z

{% raw %}<pre class="Agda"><a id="5286" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `foldr-monoid-foldl` (practice)

Show that if `_⊗_` and `e` form a monoid, then `foldr _⊗_ e` and
`foldl _⊗_ e` always compute the same result.

{% raw %}<pre class="Agda"><a id="5478" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `Any-++-⇔` (recommended)

Prove a result similar to `All-++-⇔`, but with `Any` in place of `All`, and a suitable
replacement for `_×_`.  As a consequence, demonstrate an equivalence relating
`_∈_` and `_++_`.

{% raw %}<pre class="Agda"><a id="5735" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `All-++-≃` (stretch)

Show that the equivalence `All-++-⇔` can be extended to an isomorphism.

{% raw %}<pre class="Agda"><a id="5876" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `¬Any≃All¬` (recommended)

Show that `Any` and `All` satisfy a version of De Morgan's Law:

    (¬_ ∘ Any P) xs ≃ All (¬_ ∘ P) xs

(Can you see why it is important that here `_∘_` is generalised
to arbitrary levels, as described in the section on
[universe polymorphism]({{ site.baseurl }}/Equality/#unipoly)?)

Do we also have the following?

    (¬_ ∘ All P) xs ≃ Any (¬_ ∘ P) xs

If so, prove; if not, explain why.


#### Exercise `All-∀` (practice)

Show that `All P xs` is isomorphic to `∀ {x} → x ∈ xs → P x`.

{% raw %}<pre class="Agda"><a id="6439" class="Comment">-- You code goes here</a>
</pre>{% endraw %}

#### Exercise `Any-∃` (practice)

Show that `Any P xs` is isomorphic to `∃[ x ] (x ∈ xs × P x)`.

{% raw %}<pre class="Agda"><a id="6569" class="Comment">-- You code goes here</a>
</pre>{% endraw %}

#### Exercise `any?` (stretch)

Just as `All` has analogues `all` and `All?` which determine whether a
predicate holds for every element of a list, so does `Any` have
analogues `any` and `Any?` which determine whether a predicate holds
for some element of a list.  Give their definitions.

{% raw %}<pre class="Agda"><a id="6891" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `filter?` (stretch)

Define the following variant of the traditional `filter` function on lists,
which given a decidable predicate and a list returns all elements of the
list satisfying the predicate:
{% raw %}<pre class="Agda"><a id="7139" class="Keyword">postulate</a>
  <a id="filter?"></a><a id="7151" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#7151" class="Postulate">filter?</a> <a id="7159" class="Symbol">:</a> <a id="7161" class="Symbol">∀</a> <a id="7163" class="Symbol">{</a><a id="7164" href="Assignment3.html#7164" class="Bound">A</a> <a id="7166" class="Symbol">:</a> <a id="7168" class="PrimitiveType">Set</a><a id="7171" class="Symbol">}</a> <a id="7173" class="Symbol">{</a><a id="7174" href="Assignment3.html#7174" class="Bound">P</a> <a id="7176" class="Symbol">:</a> <a id="7178" href="Assignment3.html#7164" class="Bound">A</a> <a id="7180" class="Symbol">→</a> <a id="7182" class="PrimitiveType">Set</a><a id="7185" class="Symbol">}</a>
    <a id="7191" class="Symbol">→</a> <a id="7193" class="Symbol">(</a><a id="7194" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#7194" class="Bound">P?</a> <a id="7197" class="Symbol">:</a> <a id="7199" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Unary.html#3474" class="Function">Decidable</a> <a id="7209" href="Assignment3.html#7174" class="Bound">P</a><a id="7210" class="Symbol">)</a> <a id="7212" class="Symbol">→</a> <a id="7214" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part1/Lists.md %}{% raw %}#1067" class="Datatype">List</a> <a id="7219" href="Assignment3.html#7164" class="Bound">A</a> <a id="7221" class="Symbol">→</a> <a id="7223" href="https://agda.github.io/agda-stdlib/v1.1/Data.Product.html#1783" class="Function">∃[</a> <a id="7226" href="Assignment3.html#7226" class="Bound">ys</a> <a id="7229" href="https://agda.github.io/agda-stdlib/v1.1/Data.Product.html#1783" class="Function">]</a><a id="7230" class="Symbol">(</a> <a id="7232" href="plfa.part1.Lists.html#21536" class="Datatype">All</a> <a id="7236" href="Assignment3.html#7174" class="Bound">P</a> <a id="7238" href="Assignment3.html#7226" class="Bound">ys</a> <a id="7241" class="Symbol">)</a>
</pre>{% endraw %}


## Lambda

#### Exercise `mul` (recommended)

Write out the definition of a lambda term that multiplies
two natural numbers.  Your definition may use `plus` as
defined earlier.

{% raw %}<pre class="Agda"><a id="7432" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `mulᶜ` (practice)

Write out the definition of a lambda term that multiplies
two natural numbers represented as Church numerals. Your
definition may use `plusᶜ` as defined earlier (or may not
— there are nice definitions both ways).

{% raw %}<pre class="Agda"><a id="7713" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `primed` (stretch) {#primed}

Some people find it annoying to write `` ` "x" `` instead of `x`.
We can make examples with lambda terms slightly easier to write
by adding the following definitions:
{% raw %}<pre class="Agda"><a id="ƛ′_⇒_"></a><a id="7957" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#7957" class="Function Operator">ƛ′_⇒_</a> <a id="7963" class="Symbol">:</a> <a id="7965" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3796" class="Datatype">Term</a> <a id="7970" class="Symbol">→</a> <a id="7972" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a> <a id="7977" class="Symbol">→</a> <a id="7979" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a>
<a id="7984" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#7957" class="Function Operator">ƛ′</a> <a id="7987" class="Symbol">(</a><a id="7988" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3815" class="InductiveConstructor Operator">`</a> <a id="7990" href="Assignment3.html#7990" class="Bound">x</a><a id="7991" class="Symbol">)</a> <a id="7993" href="Assignment3.html#7957" class="Function Operator">⇒</a> <a id="7995" href="Assignment3.html#7995" class="Bound">N</a>  <a id="7998" class="Symbol">=</a>  <a id="8001" href="plfa.part2.Lambda.html#3854" class="InductiveConstructor Operator">ƛ</a> <a id="8003" href="Assignment3.html#7990" class="Bound">x</a> <a id="8005" href="plfa.part2.Lambda.html#3854" class="InductiveConstructor Operator">⇒</a> <a id="8007" href="Assignment3.html#7995" class="Bound">N</a>
<a id="8009" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#7957" class="CatchallClause Function Operator">ƛ′</a><a id="8011" class="CatchallClause"> </a><a id="8012" class="CatchallClause Symbol">_</a><a id="8013" class="CatchallClause"> </a><a id="8014" href="Assignment3.html#7957" class="CatchallClause Function Operator">⇒</a><a id="8015" class="CatchallClause"> </a><a id="8016" class="CatchallClause Symbol">_</a>      <a id="8023" class="Symbol">=</a>  <a id="8026" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#294" class="Function">⊥-elim</a> <a id="8033" href="Assignment3.html#8062" class="Postulate">impossible</a>
  <a id="8046" class="Keyword">where</a> <a id="8052" class="Keyword">postulate</a> <a id="8062" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8062" class="Postulate">impossible</a> <a id="8073" class="Symbol">:</a> <a id="8075" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#279" class="Datatype">⊥</a>

<a id="case′_[zero⇒_|suc_⇒_]"></a><a id="8078" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8078" class="Function Operator">case′_[zero⇒_|suc_⇒_]</a> <a id="8100" class="Symbol">:</a> <a id="8102" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3796" class="Datatype">Term</a> <a id="8107" class="Symbol">→</a> <a id="8109" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a> <a id="8114" class="Symbol">→</a> <a id="8116" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a> <a id="8121" class="Symbol">→</a> <a id="8123" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a> <a id="8128" class="Symbol">→</a> <a id="8130" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a>
<a id="8135" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8078" class="Function Operator">case′</a> <a id="8141" href="Assignment3.html#8141" class="Bound">L</a> <a id="8143" href="Assignment3.html#8078" class="Function Operator">[zero⇒</a> <a id="8150" href="Assignment3.html#8150" class="Bound">M</a> <a id="8152" href="Assignment3.html#8078" class="Function Operator">|suc</a> <a id="8157" class="Symbol">(</a><a id="8158" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3815" class="InductiveConstructor Operator">`</a> <a id="8160" href="Assignment3.html#8160" class="Bound">x</a><a id="8161" class="Symbol">)</a> <a id="8163" href="Assignment3.html#8078" class="Function Operator">⇒</a> <a id="8165" href="Assignment3.html#8165" class="Bound">N</a> <a id="8167" href="Assignment3.html#8078" class="Function Operator">]</a>  <a id="8170" class="Symbol">=</a>  <a id="8173" href="plfa.part2.Lambda.html#4023" class="InductiveConstructor Operator">case</a> <a id="8178" href="Assignment3.html#8141" class="Bound">L</a> <a id="8180" href="plfa.part2.Lambda.html#4023" class="InductiveConstructor Operator">[zero⇒</a> <a id="8187" href="Assignment3.html#8150" class="Bound">M</a> <a id="8189" href="plfa.part2.Lambda.html#4023" class="InductiveConstructor Operator">|suc</a> <a id="8194" href="Assignment3.html#8160" class="Bound">x</a> <a id="8196" href="plfa.part2.Lambda.html#4023" class="InductiveConstructor Operator">⇒</a> <a id="8198" href="Assignment3.html#8165" class="Bound">N</a> <a id="8200" href="plfa.part2.Lambda.html#4023" class="InductiveConstructor Operator">]</a>
<a id="8202" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8078" class="CatchallClause Function Operator">case′</a><a id="8207" class="CatchallClause"> </a><a id="8208" class="CatchallClause Symbol">_</a><a id="8209" class="CatchallClause"> </a><a id="8210" href="Assignment3.html#8078" class="CatchallClause Function Operator">[zero⇒</a><a id="8216" class="CatchallClause"> </a><a id="8217" class="CatchallClause Symbol">_</a><a id="8218" class="CatchallClause"> </a><a id="8219" href="Assignment3.html#8078" class="CatchallClause Function Operator">|suc</a><a id="8223" class="CatchallClause"> </a><a id="8224" class="CatchallClause Symbol">_</a><a id="8225" class="CatchallClause"> </a><a id="8226" href="Assignment3.html#8078" class="CatchallClause Function Operator">⇒</a><a id="8227" class="CatchallClause"> </a><a id="8228" class="CatchallClause Symbol">_</a><a id="8229" class="CatchallClause"> </a><a id="8230" href="Assignment3.html#8078" class="CatchallClause Function Operator">]</a>      <a id="8237" class="Symbol">=</a>  <a id="8240" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#294" class="Function">⊥-elim</a> <a id="8247" href="Assignment3.html#8276" class="Postulate">impossible</a>
  <a id="8260" class="Keyword">where</a> <a id="8266" class="Keyword">postulate</a> <a id="8276" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8276" class="Postulate">impossible</a> <a id="8287" class="Symbol">:</a> <a id="8289" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#279" class="Datatype">⊥</a>

<a id="μ′_⇒_"></a><a id="8292" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8292" class="Function Operator">μ′_⇒_</a> <a id="8298" class="Symbol">:</a> <a id="8300" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3796" class="Datatype">Term</a> <a id="8305" class="Symbol">→</a> <a id="8307" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a> <a id="8312" class="Symbol">→</a> <a id="8314" href="plfa.part2.Lambda.html#3796" class="Datatype">Term</a>
<a id="8319" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8292" class="Function Operator">μ′</a> <a id="8322" class="Symbol">(</a><a id="8323" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3815" class="InductiveConstructor Operator">`</a> <a id="8325" href="Assignment3.html#8325" class="Bound">x</a><a id="8326" class="Symbol">)</a> <a id="8328" href="Assignment3.html#8292" class="Function Operator">⇒</a> <a id="8330" href="Assignment3.html#8330" class="Bound">N</a>  <a id="8333" class="Symbol">=</a>  <a id="8336" href="plfa.part2.Lambda.html#4083" class="InductiveConstructor Operator">μ</a> <a id="8338" href="Assignment3.html#8325" class="Bound">x</a> <a id="8340" href="plfa.part2.Lambda.html#4083" class="InductiveConstructor Operator">⇒</a> <a id="8342" href="Assignment3.html#8330" class="Bound">N</a>
<a id="8344" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8292" class="CatchallClause Function Operator">μ′</a><a id="8346" class="CatchallClause"> </a><a id="8347" class="CatchallClause Symbol">_</a><a id="8348" class="CatchallClause"> </a><a id="8349" href="Assignment3.html#8292" class="CatchallClause Function Operator">⇒</a><a id="8350" class="CatchallClause"> </a><a id="8351" class="CatchallClause Symbol">_</a>      <a id="8358" class="Symbol">=</a>  <a id="8361" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#294" class="Function">⊥-elim</a> <a id="8368" href="Assignment3.html#8397" class="Postulate">impossible</a>
  <a id="8381" class="Keyword">where</a> <a id="8387" class="Keyword">postulate</a> <a id="8397" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8397" class="Postulate">impossible</a> <a id="8408" class="Symbol">:</a> <a id="8410" href="https://agda.github.io/agda-stdlib/v1.1/Data.Empty.html#279" class="Datatype">⊥</a>
</pre>{% endraw %}We intend to apply the function only when the first term is a variable, which we
indicate by postulating a term `impossible` of the empty type `⊥`.  If we use
C-c C-n to normalise the term

  ƛ′ two ⇒ two

Agda will return an answer warning us that the impossible has occurred:

  ⊥-elim (plfa.part2.Lambda.impossible (`` `suc (`suc `zero)) (`suc (`suc `zero)) ``)

While postulating the impossible is a useful technique, it must be
used with care, since such postulation could allow us to provide
evidence of _any_ proposition whatsoever, regardless of its truth.

The definition of `plus` can now be written as follows:
{% raw %}<pre class="Agda"><a id="plus′"></a><a id="9042" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#9042" class="Function">plus′</a> <a id="9048" class="Symbol">:</a> <a id="9050" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3796" class="Datatype">Term</a>
<a id="9055" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#9042" class="Function">plus′</a> <a id="9061" class="Symbol">=</a> <a id="9063" href="Assignment3.html#8292" class="Function Operator">μ′</a> <a id="9066" href="Assignment3.html#9173" class="Function">+</a> <a id="9068" href="Assignment3.html#8292" class="Function Operator">⇒</a> <a id="9070" href="Assignment3.html#7957" class="Function Operator">ƛ′</a> <a id="9073" href="Assignment3.html#9187" class="Function">m</a> <a id="9075" href="Assignment3.html#7957" class="Function Operator">⇒</a> <a id="9077" href="Assignment3.html#7957" class="Function Operator">ƛ′</a> <a id="9080" href="Assignment3.html#9201" class="Function">n</a> <a id="9082" href="Assignment3.html#7957" class="Function Operator">⇒</a>
          <a id="9094" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8078" class="Function Operator">case′</a> <a id="9100" href="Assignment3.html#9187" class="Function">m</a>
            <a id="9114" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8078" class="Function Operator">[zero⇒</a> <a id="9121" href="Assignment3.html#9201" class="Function">n</a>
            <a id="9135" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#8078" class="Function Operator">|suc</a> <a id="9140" href="Assignment3.html#9187" class="Function">m</a> <a id="9142" href="Assignment3.html#8078" class="Function Operator">⇒</a> <a id="9144" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3982" class="InductiveConstructor Operator">`suc</a> <a id="9149" class="Symbol">(</a><a id="9150" href="Assignment3.html#9173" class="Function">+</a> <a id="9152" href="plfa.part2.Lambda.html#3900" class="InductiveConstructor Operator">·</a> <a id="9154" href="Assignment3.html#9187" class="Function">m</a> <a id="9156" href="plfa.part2.Lambda.html#3900" class="InductiveConstructor Operator">·</a> <a id="9158" href="Assignment3.html#9201" class="Function">n</a><a id="9159" class="Symbol">)</a> <a id="9161" href="Assignment3.html#8078" class="Function Operator">]</a>
  <a id="9165" class="Keyword">where</a>
  <a id="9173" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#9173" class="Function">+</a>  <a id="9176" class="Symbol">=</a>  <a id="9179" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3815" class="InductiveConstructor Operator">`</a> <a id="9181" class="String">&quot;+&quot;</a>
  <a id="9187" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#9187" class="Function">m</a>  <a id="9190" class="Symbol">=</a>  <a id="9193" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3815" class="InductiveConstructor Operator">`</a> <a id="9195" class="String">&quot;m&quot;</a>
  <a id="9201" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#9201" class="Function">n</a>  <a id="9204" class="Symbol">=</a>  <a id="9207" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#3815" class="InductiveConstructor Operator">`</a> <a id="9209" class="String">&quot;n&quot;</a>
</pre>{% endraw %}Write out the definition of multiplication in the same style.


#### Exercise `_[_:=_]′` (stretch)

The definition of substitution above has three clauses (`ƛ`, `case`,
and `μ`) that invoke a `with` clause to deal with bound variables.
Rewrite the definition to factor the common part of these three
clauses into a single function, defined by mutual recursion with
substitution.

{% raw %}<pre class="Agda"><a id="9601" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `—↠≲—↠′` (practice)

Show that the first notion of reflexive and transitive closure
above embeds into the second. Why are they not isomorphic?

{% raw %}<pre class="Agda"><a id="9792" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `plus-example` (practice)

Write out the reduction sequence demonstrating that one plus one is two.

{% raw %}<pre class="Agda"><a id="9939" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `Context-≃` (practice)

Show that `Context` is isomorphic to `List (Id × Type)`.
For instance, the isomorphism relates the context

    ∅ , "s" ⦂ `ℕ ⇒ `ℕ , "z" ⦂ `ℕ

to the list

    [ ⟨ "z" , `ℕ ⟩ , ⟨ "s" , `ℕ ⇒ `ℕ ⟩ ]

{% raw %}<pre class="Agda"><a id="10207" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `mul-type` (recommended)

Using the term `mul` you defined earlier, write out the derivation
showing that it is well typed.

{% raw %}<pre class="Agda"><a id="10378" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `mulᶜ-type` (practice)

Using the term `mulᶜ` you defined earlier, write out the derivation
showing that it is well typed.

{% raw %}<pre class="Agda"><a id="10549" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}


## Properties

#### Exercise `Progress-≃` (practice)

Show that `Progress M` is isomorphic to `Value M ⊎ ∃[ N ](M —→ N)`.

{% raw %}<pre class="Agda"><a id="10706" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `progress′` (practice)

Write out the proof of `progress′` in full, and compare it to the
proof of `progress` above.

{% raw %}<pre class="Agda"><a id="10870" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `value?` (practice)

Combine `progress` and `—→¬V` to write a program that decides
whether a well-typed term is a value:
{% raw %}<pre class="Agda"><a id="11037" class="Keyword">postulate</a>
  <a id="value?"></a><a id="11049" href="{% endraw %}{{ site.baseurl }}{% link out/tspl/2019/Assignment3.md %}{% raw %}#11049" class="Postulate">value?</a> <a id="11056" class="Symbol">:</a> <a id="11058" class="Symbol">∀</a> <a id="11060" class="Symbol">{</a><a id="11061" href="Assignment3.html#11061" class="Bound">A</a> <a id="11063" href="Assignment3.html#11063" class="Bound">M</a><a id="11064" class="Symbol">}</a> <a id="11066" class="Symbol">→</a> <a id="11068" href="{% endraw %}{{ site.baseurl }}{% link out/plfa/part2/Lambda.md %}{% raw %}#31710" class="InductiveConstructor">∅</a> <a id="11070" href="plfa.part2.Lambda.html#34086" class="Datatype Operator">⊢</a> <a id="11072" href="Assignment3.html#11063" class="Bound">M</a> <a id="11074" href="plfa.part2.Lambda.html#34086" class="Datatype Operator">⦂</a> <a id="11076" href="Assignment3.html#11061" class="Bound">A</a> <a id="11078" class="Symbol">→</a> <a id="11080" href="https://agda.github.io/agda-stdlib/v1.1/Relation.Nullary.html#605" class="Datatype">Dec</a> <a id="11084" class="Symbol">(</a><a id="11085" href="plfa.part2.Lambda.html#12171" class="Datatype">Value</a> <a id="11091" href="Assignment3.html#11063" class="Bound">M</a><a id="11092" class="Symbol">)</a>
</pre>{% endraw %}
#### Exercise `subst′` (stretch)

Rewrite `subst` to work with the modified definition `_[_:=_]′`
from the exercise in the previous chapter.  As before, this
should factor dealing with bound variables into a single function,
defined by mutual recursion with the proof that substitution
preserves types.

{% raw %}<pre class="Agda"><a id="11407" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `mul-eval` (recommended)

Using the evaluator, confirm that two times two is four.

{% raw %}<pre class="Agda"><a id="11538" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise: `progress-preservation` (practice)

Without peeking at their statements above, write down the progress
and preservation theorems for the simply typed lambda-calculus.

{% raw %}<pre class="Agda"><a id="11754" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `subject_expansion` (practice)

We say that `M` _reduces_ to `N` if `M —→ N`,
but we can also describe the same situation by saying
that `N` _expands_ to `M`.
The preservation property is sometimes called _subject reduction_.
Its opposite is _subject expansion_, which holds if
`M —→ N` and `∅ ⊢ N ⦂ A` imply `∅ ⊢ M ⦂ A`.
Find two counter-examples to subject expansion, one
with case expressions and one not involving case expressions.

{% raw %}<pre class="Agda"><a id="12238" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}

#### Exercise `stuck` (practice)

Give an example of an ill-typed term that does get stuck.

{% raw %}<pre class="Agda"><a id="12364" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}
#### Exercise `unstuck` (recommended)

Provide proofs of the three postulates, `unstuck`, `preserves`, and `wttdgs` above.

{% raw %}<pre class="Agda"><a id="12520" class="Comment">-- Your code goes here</a>
</pre>{% endraw %}