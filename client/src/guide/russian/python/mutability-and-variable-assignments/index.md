---
title: Python Mutability and Variable Assignments
localeTitle: Mutability Python и назначения переменных
---
> Каждый объект имеет идентификатор, тип и значение. Идентификация объекта никогда не изменяется после его создания; вы можете думать об этом как о адресе объекта в памяти. [источник](https://docs.python.org/3/reference/datamodel.html#data-model)

После создания `object` тип и идентификатор не могут быть изменены. Независимо от того, изменится ли значение (ы) объекта после его создания, определяет, является ли объект изменчивым (может изменяться) или неизменным (не может измениться).

До сих пор мы узнали о нескольких типах объектов и их подклассах: `string` и числовых (целых, плавающих, сложных и логических) объектах. Все это **неизменные** объекты.

Сначала эта концепция может сбивать с толку, потому что то, что хорошо, является объектом, если вы не можете его изменить. То, что делает эти объекты полезными, - это возможность назначать и переназначать переменные. Функции и операторы могут возвращать новые объекты, которые могут быть назначены переменным.

Используя встроенную [функцию id](https://docs.python.org/3/library/functions.html#id) , которая возвращает идентификатор объекта, мы можем видеть, как это работает.

Вот несколько вещей, которые нужно иметь в виду:

*   Назначение переменной не означает, что _переменная_ является _объектом_ . Мы использовали очень специфический язык, отметив, что _операторы присваивания_ **связывают** **имя** (идентификатор) с _объектом_ . Переменные можно переназначить:

\`питон

> > > a = 1 # Привязать к объекту.  
> > > Ида)  
> > > 140355241530152  
> > > a = 2 # Перевяжите a другому объекту.  
> > > Ида)  
> > > 140355241530128  
> > > \`

*   Присвоение двух разных переменных _неизменяемым объектам_ с одинаковым значением может привести (не гарантируется) к ним, связанным с одним и тем же _объектом_

\`питон

> > > a = 1  
> > > b = 1  
> > > Ида)  
> > > 140355241530152  
> > > id (b) # В этом случае a и b привязаны к одному и тому же объекту.  
> > > 140355241530152  
> > > \`

*   Назначение двух разных переменных для _объектов_ с разными значениями всегда приведет к их привязке к различным _объектам_ :

\`питон

> > > a = 1  
> > > b = 2  
> > > Ида)  
> > > 140355241530152  
> > > id (b) # a и b связаны с разными объектами.  
> > > 140355241530128  
> > > \`

*   Переназначение переменных не изменяет исходный объект, он связывает их с другим объектом.

\`питон

> > > a = 1  
> > > b = 1  
> > > Ида)  
> > > 140355241530152  
> > > Идентификатор (б)  
> > > 140355241530152  
> > > a = 2  
> > > id (a) # a - отскок другого объекта.  
> > > 140355241530128  
> > > id (b) # b все еще привязан к исходному объекту.  
> > > 140355241530152  
> > > \`