# Les nombres rationels

## Les nombres entiers naturels
On note l'ensembles des entiers naturels $\mathbb N = \{0,1, 2, 3, \ldots \}$. 

Les nombres entiers sont caractérisé par le fait que chaque nombre $n$ admet un, et un seul, succeseur $n+1$. On se convainc donc que l'ensemble $\mathbb N$ est infini.

```{admonition} Principe de recurence
Soit $P(n)$ une propriété qui depend d'un entier naturel $n$. Supposons que:
- $P(0)$ est vrai;
- $\forall n \in \mathbb N$, ($P(n)$ est vrai) $\rightarrow (P(n+1)$ est vrai).

Alors la propiété est vrai pour tout $n \in \mathbb N$.
```

```{admonition} Propriétés des nombres entiers
 $\forall m, n, p \in \mathbb N$:
- $m+n=n+m \in \mathbb N$;
- $(m+n)+p = m+(n+p) =:m+n+p$;
- $m\times n = n\times m \in \mathbb N$;
- $(m\times n)\times p = m\times(n\times p)$;
- $(m+n)\times p = (m\times p) + (n\times p)$;
- $m+p = n +p \rightarrow m=n$;
- si $m+n=0$ alors $m=n=0$;
- si $ m\times n = 0$ alors $m=0$ ou $n=0$;
- si $ m\times p = n\times p$ et $p>0$ alors $m=n$;
- $ m \leq m$;
- si $ m \leq n$ et $n\leq p$ alors $m\leq p$;
- $m \leq n$ si et seulement si $ m+c \leq n + c$;
- si $m<n$ et $p>0$ alors $m\times p < n\times p$;
- si $m<n$ alors $m+1 \leq n$;
- $m<n$ si et seulement si $\exits d\in \mathbb N$ tel que $m=n+d$ et $d>0$
- l'ordre est total : exactement l'une des assertions suivantes est correcte: 
    - $m<n$;
    - $m>n$;
    - $m=n$.
```
Les opérations soustraction et division sont aussi possibles dans $\mathbb N$. Cependant, leur résultats n'est pas toujours dans $\mathbb N$. Nous allons les voir dans les sections suivantes.

```{admonition} Proposition (Algorithme d'Euclid)
Soient $n\in \mathbb N$ et $q\in \mathbb N\setminus0$. Alors 

$$
\exists m,r \in \mathbb N, 0\leq r<q \mbox{ et } n = mq +r
$$

```



## Les nombres entiers relatifs

```{admonition} Définition
Un entier relatif est une expression de la forme $m-n$ où $m$ et $n$ sont des entiers naturels. Deux entiers relatifs sont considérés égales $m-n = p-q$ si et seulement si $m+q=n+p$. L'ensemble de ces nombres est noté $\mathbb Z$.

```
Roles and directives are two of the most powerful tools in Jupyter Book. They
are kind of like functions, but written in a markup language. They both
serve a similar purpose, but **roles are written in one line**, whereas
**directives span many lines**. They both accept different kinds of inputs,
and what they do with those inputs depends on the specific role or directive
that is being called.

### Using a directive

At its simplest, you can insert a directive into your book's content like so:

````
```{mydirectivename}
My directive content
```
````

This will only work if a directive with name `mydirectivename` already exists
(which it doesn't). There are many pre-defined directives associated with
Jupyter Book. For example, to insert a note box into your content, you can
use the following directive:

````
```{note}
Here is a note
```
````

This results in:

```{note}
Here is a note
```

In your built book.

For more information on writing directives, see the
[MyST documentation](https://myst-parser.readthedocs.io/).


### Using a role

Roles are very similar to directives, but they are less-complex and written
entirely on one line. You can insert a role into your book's content with
this pattern:

```
Some content {rolename}`and here is my role's content!`
```

Again, roles will only work if `rolename` is a valid role's name. For example,
the `doc` role can be used to refer to another page in your book. You can
refer directly to another page by its relative path. For example, the
role syntax `` {doc}`intro` `` will result in: {doc}`intro`.

For more information on writing roles, see the
[MyST documentation](https://myst-parser.readthedocs.io/).


### Adding a citation

You can also cite references that are stored in a `bibtex` file. For example,
the following syntax: `` {cite}`holdgraf_evidence_2014` `` will render like
this: {cite}`holdgraf_evidence_2014`.

Moreoever, you can insert a bibliography into your page with this syntax:
The `{bibliography}` directive must be used for all the `{cite}` roles to
render properly.
For example, if the references for your book are stored in `references.bib`,
then the bibliography is inserted with:

````
```{bibliography}
```
````

Resulting in a rendered bibliography that looks like:

```{bibliography}
```


### Executing code in your markdown files

If you'd like to include computational content inside these markdown files,
you can use MyST Markdown to define cells that will be executed when your
book is built. Jupyter Book uses *jupytext* to do this.

First, add Jupytext metadata to the file. For example, to add Jupytext metadata
to this markdown page, run this command:

```
jupyter-book myst init markdown.md
```

Once a markdown file has Jupytext metadata in it, you can add the following
directive to run the code at build time:

````
```{code-cell}
print("Here is some code to execute")
```
````

When your book is built, the contents of any `{code-cell}` blocks will be
executed with your default Jupyter kernel, and their outputs will be displayed
in-line with the rest of your content.

For more information about executing computational content with Jupyter Book,
see [The MyST-NB documentation](https://myst-nb.readthedocs.io/).
