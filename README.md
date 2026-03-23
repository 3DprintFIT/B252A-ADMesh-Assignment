# ADMesh Assignment (CZ)

Před odevzdáním úlohy přes GitHub je třeba
[projevit souhlas se zpracováním  osobních údajů](https://courses.fit.cvut.cz/BI-3DT/cs/gdpr.html).

Za tři body na cvičení naprogramujte program v jazyce C, C++,
[Python](https://pypi.org/project/admesh/) nebo
[Ruby](https://rubygems.org/gems/radmesh/),
který pro zadaný STL soubor (první argument volání programu) najde nejvhodnější
rotaci kolem osy Z tak, aby plocha obdélníkové podstavy pomyslného opsaného
hranolu objektu byla co nejmenší – hrany pomyslného opsaného hranolu jsou
rovnoběžné s osami X, Y nebo Z.

Do repozitáře vytvořeného na odkazu https://classroom.github.com/a/96lBOz0k
dejte soubor `bestrot` s příponou `c`, `cpp`, `py` nebo `rb` podle zvoleného
jazyka (např. `bestrot.c`). Je povoleno použít pouze standardní knihovnu jazyka
a ADMesh (u Ruby RADMesh).

Ilustrační obrázek z Netfabbu ukazující opsaný hranol s obdélníkovou podstavou:

![Opsaný hranol](boundingbox.png)

(Model CC BY-NC 3.0 © [Daniel Moos](https://www.thingiverse.com/thing:50212).)

Program vypíše na standardní výstup úhel otočení (ve stupních), obsah podstavy
opsaného hranolu (ten nejlepší nalezený), a do souboru zadaného druhým
argumentem (z příkazové řádky) uloží orotovaný soubor v libovlném STL formátu
(ASCII/binary).

Příklad výstupu:

```
65
897489645.867869
```

Pro ukázku můžete použít následující STL, ale program musí umět pracovat s jakýmkoliv STL.

  * [hellskull.stl](hellskull.stl) ([CC BY-ND Ola Sundberg](https://www.thingiverse.com/thing:479949))

Vhodný úhel nalezněte bruteforce metodou pro úhly otočení v násobcích 5°
(5°, 10°, 15°, ...).

Vhodné funkce a údaje:

  * `stl_rotate_z(&stl_in, angle_in_degrees)` – rotuje kolem osy Z, o daný počet stupňů
  * `<stl_file>.stats.number_of_facets` je počet trojúhelníků v STL
  * `<stl_file>.facet_start` je ukazatel na první trojúhelník (a jde k němu přistupovat jako k poli)
  * trojúhelníky jsou uloženy v strukturách `stl_facet` obsahující v trojprvkovém poli `vertex` tři vrcholy (struktura `stl_vertex` obsahující tři floaty `x`, `y` a `z`)
  * zajímavé údaje jsou uloženy i ve `stl_file.stats`

---

# ADMesh Assignment (EN)

Before submitting the assignment via GitHub, you need to
[give consent to the processing of personal data](https://courses.fit.cvut.cz/BI-3DT/cs/gdpr.html).

For three points in the lab, write a program in C, C++,
[Python](https://pypi.org/project/admesh/) or
[Ruby](https://rubygems.org/gems/radmesh/),
which for a given STL file (first argument of the program call) finds the most suitable
rotation around the Z axis so that the area of the rectangular base of an imaginary
circumscribed prism of the object is as small as possible – the edges of the imaginary
circumscribed prism are parallel to the X, Y, or Z axes.

In the repository created at the link https://classroom.github.com/a/96lBOz0k
place a file `bestrot` with the extension `c`, `cpp`, `py` or `rb` depending on the chosen
language (e.g. `bestrot.c`). Only the standard library of the language
and ADMesh (RADMesh for Ruby) are allowed.

Illustrative image from Netfabb showing a circumscribed prism with a rectangular base:

![Circumscribed prism](boundingbox.png)

(Model CC BY-NC 3.0 © [Daniel Moos](https://www.thingiverse.com/thing:50212).)

The program prints to standard output the rotation angle (in degrees), the area of the base
of the circumscribed prism (the best one found), and saves the rotated file in any STL format
(ASCII/binary) to the file specified by the second argument (from the command line).

Example output:

```
65
897489645.867869
```

For demonstration you can use the following STL, but the program must be able to work with any STL.

  * [hellskull.stl](hellskull.stl) ([CC BY-ND Ola Sundberg](https://www.thingiverse.com/thing:479949))

Find the suitable angle using a brute force method for rotation angles in multiples of 5°
(5°, 10°, 15°, ...).

Useful functions and data:

  * `stl_rotate_z(&stl_in, angle_in_degrees)` – rotates around the Z axis by the given number of degrees
  * `<stl_file>.stats.number_of_facets` is the number of triangles in the STL
  * `<stl_file>.facet_start` is a pointer to the first triangle (and can be accessed as an array)
  * triangles are stored in `stl_facet` structures containing three vertices in a three-element array `vertex` (`stl_vertex` structure containing three floats `x`, `y`, and `z`)
  * interesting data is also stored in `stl_file.stats`
