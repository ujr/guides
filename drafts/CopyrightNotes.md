
# Copyright and Licensing

**Copyright** is a type of intellectual property (IP). It gives
its owner the exclusive right to make copies of a creative work
(e.g. literature, music, or software). Copyright originated in
16th century England: to prevent the distribution of scandalous
texts after the advent of the printing press (ca. 1450),
a monopoly was granted to the government-approved guild of
stationers to control distribution. This eventually developed
into a copyright for authors, presumably with the intention to
bind them to a stationer as their producer and distributor.
With the advent of the Internet, distribution became a lot
easier for many types of works. The benefits of copyright law
for distributors is obvious, the benefit for creators is
purported but doubtful.

In most jurisdictions, including Germany and Switzerland, the
creator of the work automatically gets an exclusive copyright.
In the U.S. before 1989, when the Berne Convention was adopted,
a **copyright notice** was required and usually looked like this:
“Copyright © 2021 John Doe” with the year of first publication
and the name of the owner, often a company name.
Adding a copyright notice is still frequently done and not wrong.
The copyright symbol has Unicode code point U+00A9; in HTML
use `&copy;`, in Windows type Alt+0169 (on the numeric keypad).
It is commonplace to substitute the character sequence `(c)`
if the © symbol is not available.

Software as a creative work is protected by copyright law.
Therefore, a software is legally unusable by others unless
either (1) you grant a **license** to (a) particular users
or (b) the public at large, or (2) you release the software
into the **public domain**. The license is essentially a promise
to not sue the user for using your software. The public domain
means that nobody claims an intellectual monopoly. Because
copyright is the default, if you intend to make your software
public domain, you must clearly say so—and because “public domain”
might not be interpreted in the sense stated here, it is better
to include an explicit license that grants all rights to everybody.

Einige Worte auf deutsch: Copyright wird mit **Urheberrecht**
übersetzt, bedeutet aber eher ein Nutzungsrecht unabhängig vom Recht,
Urheber eines Werkes zu sein. Der angelsächsische Begriff “public
domain” wird mit “Gemeinfreiheit” übersetzt und bedeutet, dass der
Urheber eines Werkes kein exklusives Nutzungsrecht hat (weil er schon
lange gestorben ist oder explizit auf dieses Recht verzichtet) und das
Werk somit von jedermann und ohne Genehmigung verwendet werden kann.

## How do you choose an appropriate license?

1. Make sure that you have a choice:
   - Your employer may require a particular license.
   - Your customer may require a particular license.
   - Upstream code may require a particular license (e.g. copyleft libraries).
2. If you do have a choice, these are the high-level options:
   - Proprietary license (contact your legal department)
   - Permissive open-source license (e.g. MIT, BSD, Apache)
   - Copyleft open-source license (the GPL licenses)
   - Public domain (consider The Unlicense)
   - No license (not recommended)
3. Resources for choosing an open-source license:
   - <https://choosealicense.com>
   - <https://opensource.org/licenses>
   - <https://tldrlegal.com>
   - <https://unlicense.org> – also has pointers to background information

## Recommendations

- If you can and want to go open source, consider the
  **MIT License** and read this interesting and approachable
  [line-by-line legal explanation](https://writing.kemitchell.com/2016/09/21/MIT-License-Line-by-Line.html).

- If you want to go public domain, use **The Unlicense** and read
  some background info at [unlicense.org](https://unlicense.org).

- If you are a teenager and want to go public domain, have a look
  at the Do What the Fuck You Want Public License
  at [www.wtfpl.net](http://www.wtfpl.net/).

- If your work is not software, consider the **Creative Commons**
  licenses at [creativecommons.org](https://creativecommons.org/).

Ein deutschsprachiges Standardwerk zu rechtlichen Fragen rund
um Open Source Software ist: Till Jaeger und Axel Metzger:
*Open Source Software. Rechtliche Rahmenbdingungen der Freien Software*.
5. Auflage, C.H.Beck, 2020. [Amazon](https://www.amazon.de/dp/3406734979)

## Summary

Having no license on a codebase makes it legally impossible
to use it because strong copyright protection is the default.
Therefore, include a license that grants actors besides the
originator the right to use your code for the stated purposes
and under the stated conditions. Place the license text in a
file called LICENSE at the root level of your codebase.

Last but not least: I'm not a lawyer. The statements above
may be wrong. I ask you to carefully check them on your own
and I disclaim all responsibility.

## References

The notes on the history of copyright in the first paragraph
are a highly condensed summary of Karl Fogel's article on
*The Surprising History of Copyright ...*
at <https://questioncopyright.org/promise>.
