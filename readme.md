- ¿Qué comando utilizaste en el paso 11? ¿Por qué?
Como queremos tener los cambios exactos del commit anterior utilizamos el siguiente comando:
 git reset --hard  HEAD~1


- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

Aplicamos git reflog con este comando identificamos el commit desecho con el siguiente identificador c370345

Para indicarle que mi rama styled apunte a ese commit c370345 lo hacemos con el siquiente comando:

git reset --hard c370345

Con esto volvemos al commit cuando se creó.

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
 
 git merge master
 Como estamos en la rama style nos dice que quiere absorber a la rama master.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
git merge htmlify , tenemos un conflicto por que tenemos que arreglar el git-nuestro.md , solo nos quedamos con lo que teniamos en la rama styled. Hacemos un commit  para reslover el merge.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
Cambiamos a la rama [mastter] con git checkout master
Como reliaza un fast-forward por que esta en la misma rama utilizamos : git merge styled
No tenemos conficto por que no se ha modificado ningun archivo para decirle con cual nos quedamos.

- ¿Qué comando o comandos utilizaste en el paso 25?

git config alias.graph "log --graph --pretty=online"
git log  -- graph

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
Si que puede ser , lo he probao con este comando.
git merge title
Lo he realizado de esa manera por que esta alineada la rama title con master. Por eso git lo toma como fast-forward.

- ¿Qué comando o comandos utilizaste en el paso 27?
Entiendo que no quedamos con los cambios donde estaba con la rama tittle aplicamos reset pero son hard:
git reset HEAD~1


- ¿Qué comando o comandos utilizaste en el paso 28?
Le decimos a git que queremos tener el trabajo que ya teniamos:
git reset <file>
Como tengo un version antigua de git esta es la opción que he sacado.
Para quedarme en este paso realizo un commit
git add git-nuestro.md
git commit -m "Descartar los cambios "

Sé que no tengo que hacer este commit pero prefiero tener este commit para trabajar.

- ¿Qué comando o comandos utilizaste en el paso 29?
git branch -D title


- ¿Qué comando o comandos utilizaste en el paso 30?
Como he borrado la rama title , lo que voy hace es dar un paso con el commit  y con reflog buscar la direccion del commit de la rama title y megear. Master absorbe title.
git reset --hard HEAD~1
git merge 44bd16b


- ¿Qué comando o comandos usaste en el paso 32?
Como estoy en la misma rama cuento los commit para retroceder tres posiciones al commit inicial.
git reset --hard HEAD~3

- ¿Qué comando o comandos usaste en el punto 33?
Hacemos un cat y nos sale lo siguiente:
		Git nuestro
		Git nuestro que estas en los repos Comprimidos sean tus commits
		Venga a nosotros tu log
		En el local como en el remote
		Danos hoy nuestro pull de cada día
		Perdona nuestros conflictos
		Como también perdonamos los de otros geeks No nos dejes caer en detached HEAD
		y líbranos de SVN
		git commit --amend

git reflog --> en el buscamos en el commit donde añadimos el titulo y tenemos el siguiente 44bd16b.
git checkout 44bd16b





