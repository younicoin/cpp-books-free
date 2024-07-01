# C++ Books Free

C++ free books. Learn C++


## C++ Primer, Fifth Edition

Authors: Stanley B. Lippman, Josée Lajoie, Barbara E. Moo

Source: https://github.com/wxx9248/CPP-Primer-5th-Edition \
Build pdf:
```
git clone https://github.com/wxx9248/CPP-Primer-5th-Edition.git
cd CPP-Primer-5th-Edition/
sed -i 's/^<table width="100%" border="0" cellspacing="0" cellpadding="0">$//g' *.html
sed -i 's/<tr><td><div STYLE="MARGIN-LEFT: 0.15in;">.*<\/div><\/td><td align="right"><div STYLE="MARGIN-LEFT: 0.15in;">//g' *.html
sed -i 's/.*<img src="images\/previous.gif" width="62" height="15" border="0" align="absmiddle" alt="Previous Section">.*//g' *.html
sed -i 's/.*<img src="images\/next.gif" width="41" height="15" border="0" align="absmiddle" alt="Next Section"><\/a><\/div><\/td><\/tr><\/table>//g' *.html
sed '$d' 000-cpp_primer_fifth_edition.html > book.html
sed -n '10,$p' {001..300}*.html | sed '$d' >> book.html
sed -n '$p' 000-cpp_primer_fifth_edition.html >> book.html
sed -i 's/\(<a href="\)\([0-9][0-9][0-9]-[^#]*\)\(#[^"]*">\)/\1\3/g' book.html
sed -i 's/\(href="\)\([0-9][0-9][0-9]-[^#]*\)\(#[^"]*"\)/\1\3/g' book.html
sed -i 's/<a\/>//g' book.html
sed -i 's/\(<[^>]*\)\/>/\1>/g' book.html
sed -i 's/\(<[^>]* id="\)\(filepos[0-9]*\)" \([^>]*>\)/<a name="\2">\&nbsp;<\/a>\1\2" \3/g' book.html
chromium book.html
chromium --headless --print-to-pdf="./CPP-Primer-5th-Edition.pdf" book.html
  (but wkhtmltopdf and firefox did not work with internal links)
```

