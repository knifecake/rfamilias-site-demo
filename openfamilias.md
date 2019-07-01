---
title: R Familias
layout: page
---

The code for the core functions of Familias has been released in an [R
package], available from CRAN. A slighty updated version is available
from [GitHub]. (Please go to [http://familias.no] for free download of
Windows Familias and documentation.) To install the package, write, in
R,

{% highlight R %}
install.packages("Familias")

library(Familias)
{% endhighlight %}

Information and help about the package can then be reached with

{% highlight R %}
help("Familias")
{% endhighlight %}

Most computations in [relMix], a program for relationship inference involving mixtures,
are done using Familias functions. For advanced [relMix] cases, pedigrees must be defined
using the Familias format. The below example gives a family with two brothers, where one of the brothers
has a child:

{% highlight R %}
persons <- c("Child", "Brother1", "Brother2", "Mother", "A", "B")
ped1 <- FamiliasPedigree(id = persons,
  dadid = c("Brother1", "A", "A", NA, NA, NA), 
  momid = c("Mother", "B", "B", NA, NA, NA), 
  sex = c("male", "male", "male", "female", "male", "female"))
{% endhighlight %}

The `plot` function can be used to visualise the pedigree. For more advanced plots
for instance displaying marker data, we recommend the [ped-suite]. The 
`Familias2ped` function in `forrel`, one of the R libraries in the
[ped-suite], converts data in Familias to the `ped` format.

  [R package]: https://CRAN.R-project.org/package=Familias
  [GitHub]: https://github.com/thoree/Familias
  [http://familias.no]: http://familias.no/
  [relMix]: https://CRAN.R-project.org/package=relMix
  [ped-suite]: https://github.com/magnusdv/pedtools
