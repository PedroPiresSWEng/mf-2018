/*

1. Qual o comando para obter a versão instalada do Git?
	git --version
		Minha versão é 2.18.0.windows.1;
2. Qual o efeito da execução de cada um dos comandos abaixo?
	git help
		Comando utilizado para esclarecer dúvidas referente aos demais comandos disponíveis na utilização do Git. Utilizando desta ferramenta, é possível detalhar as funções específicas para cada comando, detalhando quando e como utilizá-lo.
	git help reset
		Abre um arquivo .html localizado no AppData do computador em que a aplicação está instalada, contendo informações sobre a utilização do comando git reset. Nesse caso, o comando retornará o estado do repositório corrente para o último (ou outro) commit. Desfazendo as últimas alterações no repositório.
	git init
		Cria um novo repositório em um diretório existente; Ao digitar git init, o git cria (inicializa) um repositório vazio criando um repositório .git, que contém todos os arquivos necessários.
	git add --all
		Prepara todos os arquivos da árvore de trabalho para envio, tanto aqueles que já possuem entry matching, fazendo updates (de maneira geral, quando o arquivo já possuía versão criada no repositório) quanto novos arquivos e pastas. Podendo, inclusive, excluir ou criar novos diretórios inseridos no commit.
	git add -u
		Realiza commit apenas dos arquivos que já possuem versão inserida no repositório. Esse comando remove arquivos para adequar à árvore de trabalho, mas não cria novs arquivos.
	git config -l
		Comando que lista todas as configurações do seu git, desde sua forma de operar à sua aparência.
			
			Meu git está configurado da seguinte forma:

			core.symlinks=false
			core.autocrlf=true
			core.fscache=true
			color.diff=auto
			color.status=auto
			color.branch=auto
			color.interactive=true
			help.format=html
			rebase.autosquash=true
			http.sslcainfo=C:/Users/EnsuBroker Consult/AppData/Local/Programs/Git/mingw64/ssl/certs/ca-bundle.crt
			http.sslbackend=openssl
			diff.astextplain.textconv=astextplain
			filter.lfs.clean=git-lfs clean -- %f
			filter.lfs.smudge=git-lfs smudge -- %f
			filter.lfs.process=git-lfs filter-process
			filter.lfs.required=true
			credential.helper=manager
			user.email=pedrinxx1@gmail.com
			user.name=PedroPiresSWEng
			core.repositoryformatversion=0
			core.filemode=false
			core.bare=false
			core.logallrefupdates=true
			core.symlinks=false
			core.ignorecase=true
			remote.origin.url=https://github.com/PedroPiresSWEng/mf-2018.git
			remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
			branch.master.remote=origin
			branch.master.merge=refs/heads/master
	git mv a.txt b.txt
		Nesse caso, o git está alterando via comando mv o nome do arquivo a.txt para b.txt. 
	git reset --hard
		Este comando fará com que todas as alterações no diretório de trabalho seja descartado para o último commit.
	git log -27
		O comando git log é utilizado para listas o histórico de modificações no repositório. Ao definir um valor inteiro (-n), você define a quantidade de logs que deseja visualizar. Neste caso, aparecerão os últimos 27 logs. 
			No meu caso o comando resultou nas seguintes informações:
				$ git log -27
				commit f169ff30751eb198acef4e8e01fd70da6f27e501 (HEAD -> master, origin/master, origin/HEAD)
				Author: PedroPiresSWEng <pedrinxx1@gmail.com>
				Date:   Mon Sep 10 19:48:07 2018 -0300

				    Inclusao da aula 2

				commit 032fbe5b21ccb46218e730910b0e86280eb9d844
				Author: Pedro Pires <pedrinxx1@gmail.com>
				Date:   Mon Aug 20 21:12:40 2018 -0300

				    Update README.md

				commit 0df12675b224b57e0816c79169112bae0690dbc6
				Author: Pedro Pires <pedrinxx1@gmail.com>
				Date:   Mon Aug 20 21:11:55 2018 -0300

				    Update README.md

				commit 31e7b3a15801b11d2a8cd2d58c040f0750591877
				Author: Pedro Pires <pedrinxx1@gmail.com>
				Date:   Mon Aug 20 21:10:23 2018 -0300

				    Initial commit
3. O fluxo “clássico” de interação com o Git é algo como “alterar um ou mais arquivos”, “acrescentar essas mudanças para serem contemplados no próximo commit” e, finalmente, executar um “commit”. Quais os comandos necessários para realizar os dois últimos “passos” desse fluxo?
	Acrescentar mudanças para realizar um commit:
		O comando utilizados para carregar as mudanças para a Staged Area, é o git add. É indicado após as devidas alterações no repositório, listar todas as alterações por meio do comando git status.
	Executar um commit
		Para realizar o commit, utilize o comando git commit (pode utilizar -m seguido de um comentário entre "" para escrever observações no commit).
		Após realização do commit, utilize o comando git push para enviar suas alterações ao repositório na nuvem.
4. Qual o comando deve ser executado para identificar o que foi alterado desde o último “commit”?
		O comando que eu utilizo é o git status;
5. Em um dado repositório, arquivos simplesmente copiados para lá, ou seja, untracked, podem ser exibidos/identificados com que comando?
	git status -u
		No meu terminal, como não havia a pasta aula-3/lista.md criada no diretório da nuvem, ele listou o arquivo como untracked.
			$ git status -u
			On branch master
			Your branch is up to date with 'origin/master'.

			Untracked files:
			  (use "git add <file>..." to include in what will be committed)

			        aula-3/lista.md

			nothing added to commit but untracked files present (use "git add" to track)
6. Qual o comando para efetuar um commit?
	git commit
7. Qual o comando que devemos empregar para descartar mudanças ocorridas no arquivo teste.txt, por exemplo?
	git checkout --teste.txt
8. O que deve ser feito para que um determinado diretório do seu repositório seja ignorado pelo Git? Faça uma busca por .gitignore.
	o comando .gitignore será criado para definir quais arquivos serão ignorados pelo git. Ou seja, não serão adicionados ao repositório. Neste caso específico, para ignorar um diretório, basta realizar o comando echo "pastaignorada/" >> .gitignore. Este comando escreverá dentro do arquivo gitignore o nome do diretório que você deseja ignorar.
9. O que acontece se o seu repositório local for acidentalmente removido?
	Haverá o backup na nuvem do github e você pode clonar a última versão do repositório referente ao último commit realizado.
10. Como clonar um repositório remoto?
	Basta utilizar o comando git clone URL.do.repositorio.
11. Em alguns cenários git log pode produzir extensos resultados. Se houver interesse em visualizar o histórico de um repositório, onde cada mudança é fornecida exatamente em uma única linha, qual o comando que deve ser empregado?
	A formatação de saída --pretty do comando log mostrará os commits em formatos alternativos. (oneline, short, full, fuller, etc). Para exibir os commits em uma única linha para cada, basta digitar git log --pretty=oneline.
		$ git log --pretty=oneline
		f169ff30751eb198acef4e8e01fd70da6f27e501 (HEAD -> master, origin/master, origin/HEAD) Inclusao da aula 2
		032fbe5b21ccb46218e730910b0e86280eb9d844 Update README.md
		0df12675b224b57e0816c79169112bae0690dbc6 Update README.md
		31e7b3a15801b11d2a8cd2d58c040f0750591877 Initial commit
12. Em qual arquivo o Git armazena informações de configuração empregadas por usuário?
	/etc/gitconfig
13. Qual o comando para criar um repositório local?
	mkdir nome.do.diretorio
14. Qual o nome do diretório criado pelo Git quando se executa o comando git init?
	.git
15. Qual o comando para adicionar todos os arquivos modificados? (Aqueles para os quais git status identificam como modified?)
	git commit
16. O Git faz uso do valor de hash conhecido por SHA1. O que isto significa? Qual o propósito? O que é SHA1?
	Estudar para entender: https://git-scm.com/book/pt-br/v1/Git-Internamente-Objetos-do-Git
17. Qual a palavra para indicar o último commit em vez do valor de hash SHA1 correspondente?
	Creio que seja o diff. git diff mostra as linhas exatas que foram adicionadas e removidas. o Patch.
18. Quando se cria dois arquivos usando um editor de texto qualquer e, na sequência, executamos o comando git add -u, os dois arquivos criados passam de untracked para new file?
	Não. Esse comando apenas atualiza os documentos já existentes em seu repositorio na nuvem. 
		EnsuBroker Consult@Pedrugs MINGW64 /c/github/mf-2018 (master)
		$ cd aula-3

		EnsuBroker Consult@Pedrugs MINGW64 /c/github/mf-2018/aula-3 (master)
		$ git status
		On branch master
		Your branch is up to date with 'origin/master'.

		Untracked files:
		  (use "git add <file>..." to include in what will be committed)

		        ./

		nothing added to commit but untracked files present (use "git add" to track)

		EnsuBroker Consult@Pedrugs MINGW64 /c/github/mf-2018/aula-3 (master)
		$ git add -u

		EnsuBroker Consult@Pedrugs MINGW64 /c/github/mf-2018/aula-3 (master)
		$ git status
		On branch master
		Your branch is up to date with 'origin/master'.

		Untracked files:
		  (use "git add <file>..." to include in what will be committed)

		        ./

		nothing added to commit but untracked files present (use "git add" to track)
19. Qual o efeito da execução dos dois comandos abaixo, nesta ordem, em um dado repositório?
	git reset --soft HEAD~1
		Você desfaz o último commit, mas as alterações dos arquivos continuaram no diretório de trabalho e no index. Ou seja, se realizar um git commit criará um commit com as mesmas alterações que foram removidas.
	git reset --hard
		Você perde todas as alterações do último commit. Se você utilizar um git status, não haverá nenhuma mudança em seu repositório.
20. Após o emprego de um ambiente integrado de desenvolvimento (IDE), é comum a criação de arquivos e diretórios. Qual o comando que podemos empregar para remover arquivos e diretórios untracked?
	Podemos utilizar o comando git clean -f ou comandos como o rm para excluir arquivos específicos. Contudo, se o arquivo está como untracked não há versionamento. Logo, não será possível recuperar o arquivo após exclusão.
21. Qual o nome do arquivo no qual podemos inserir a indicação para o Git de arquivos e diretórios a serem ignorados?
	gitignore
22. Quando se cria o arquivo MinhaClasse.class em um dado diretório e desejamos que arquivos com a extensão .class, como neste caso, sejam ignorados por todos os membros de uma equipe que estão contribuindo com um dado projeto, como devemos proceder?
	Devemos, primeiro, criar o arquivo gitignore por meio do comando git add .gitignore e, posteriormente, inserir a extensão que deve ser ignorada. Neste caso, por meio do comando echo ".class" >> .gitignore.
23. jQuery é uma famosa biblioteca em JavaScript. Consulte detalhes em http://jquery.com. O repositório correspondente encontra-se em https://github.com/jquery/jquery.git. Faça o clone deste repositório.
	EnsuBroker Consult@Pedrugs MINGW64 /c/github (master)
	$ git clone https://github.com/jquery/jquery.git
	Cloning into 'jquery'...
	remote: Counting objects: 42896, done.
	remote: Compressing objects: 100% (14/14), done.
	remote: Total 42896 (delta 1), reused 3 (delta 0), pack-reused 42882
	Receiving objects: 100% (42896/42896), 27.33 MiB | 3.62 MiB/s, done.
	Resolving deltas: 100% (30353/30353), done.
24. No repositório jqueryrepo, criado no passo anterior, qual o efeito do comando 
git shortlog -sne?
	O git apresentou uma lista de cada commit, descrevendo apenas o Autor, o e-mail e a quantidade de alterações por user. 
	   269  Richard Gibson <richard.gibson@gmail.com>
	   251  Michał Gołębiowski-Owczarek <m.goleb@gmail.com>
	   250  Brandon Aaron <brandon.aaron@gmail.com>
	   200  Ariel Flesler <aflesler@gmail.com>
	    85  Mike Sherov <mike.sherov@gmail.com>
	    71  Colin Snover <github.com@zetafleet.com>
	    67  David Serduke <davidserduke@gmail.com>
	    59  Yehuda Katz <wycats@gmail.com>
	    55  Corey Frang <gnarf37@gmail.com>
	    47  Louis-Rémi Babé <lrbabe@gmail.com>
	    35  Anton Matzneller <obhvsbypqghgc@gmail.com>
	    34  Scott González <scott.gonzalez@gmail.com>
	    27  Gilles van den Hoven <gilles0181@gmail.com>
	    27  Timo Tijhof <krinklemail@gmail.com>
	    22  Robert Katić <robert.katic@gmail.com>
	    18  Jason Bedard <jason+github@jbedard.ca>
	    17  Dan Heberden <danheberden@gmail.com>
	    15  Carl Fürstenberg <azatoth@gmail.com>
	    12  Ben Alman <cowboy@rj3.net>
	    12  Karl Swedberg <kswedberg@gmail.com>
	    11  Jordan Boesch <jboesch26@gmail.com>
	    11  Mike Alsup <malsup@gmail.com>
	    10  Elijah Manor <elijah.manor@gmail.com>
	     9  Mathias Bynens <mathias@qiwi.be>
	     9  Paul Bakaus <paul.bakaus@gmail.com>
	     9  Sindre Sorhus <sindresorhus@gmail.com>
	     8  Ed Engelhardt <edengelhardt@gmail.com>
	     7  Adam J. Sontag <ajpiano@ajpiano.com>
	     7  Chris Antaki <ChrisAntaki@gmail.com>
	     7  Douglas Neiner <doug@dougneiner.com>
	     7  Gianni Alessandro Chiappetta <gianni@runlevel6.org>
	     7  James Huston <james@jameshuston.net>
	     7  Richard D. Worth <rdworth@gmail.com>
	     7  Stefan Petre <stefan.petre@gmail.com>
	     7  Xavi Ramirez <xavi.rmz@gmail.com>
	     6  Corey Jewett <cj@syntheticplayground.com>
	     6  James Burke <jrburke@gmail.com>
	     6  Klaus Hartl <klaus.hartl@gmail.com>
	     6  Scott Jehl <scottjehl@gmail.com>
	     6  Thomas Tortorini <thomastortorini@gmail.com>
	     5  Alex Sexton <AlexSexton@gmail.com>
	     5  Alexander Farkas <info@corrupt-system.de>
	     5  Charles McNulty <cmcnulty@kznf.com>
	     5  Daniel Herman <daniel.c.herman@gmail.com>
	     5  Dave Reed <dareed@microsoft.com>
	     5  Erick Ruiz de Chávez <erickrdch@gmail.com>
	     5  Sean Catchpole <littlecooldude@gmail.com>
	     4  Alexander Lisianoi <all3fox@gmail.com>
	     4  Henri Wiechers <hwiechers@gmail.com>
	     4  Iraê Carvalho <irae@irae.pro.br>
	     4  Jason Bedard <jason+jquery@jbedard.ca>
	     4  Jephte Clain <Jephte.Clain@univ-reunion.fr>
	     4  Justin Meyer <justinbmeyer@gmail.com>
	     4  Michael Bensoussan <mickey@seesmic.com>
	     3  Aditya Raghavan <araghavan3@gmail.com>
	     3  David Petersen <public@petersendidit.com>
	     3  Franck Marcia <franck.marcia@gmail.com>
	     3  Jay Merrifield <fracmak@gmail.com>
	     3  Leonardo Braga <leonardo.braga@gmail.com>
	     3  Michael Geary <mike@geary.com>
	     3  Nguyen Phuc Lam <ruado1987@gmail.com>
	     3  Paul Irish <paul.irish@gmail.com>
	     3  Paul Ramos <paul.b.ramos@gmail.com>
   		 3  Sai Lung Wong <sai.wong@huffingtonpost.com>
	     3  Saptak Sengupta <saptak013@gmail.com>
	     3  Steve Mao <maochenyan@gmail.com>
	     2  Alex Padilla <alexonezero@outlook.com>
	     2  Amey Sakhadeo <me@ameyms.com>
	     2  Anthony Ryan <anthonyryan1@gmail.com>
	     2  Anton Ryzhov <anton@ryzhov.me>
	     2  Arne de Bree <arne@bukkie.nl>
	     2  Arthur Verschaeve <contact@arthurverschaeve.be>
	     2  Aurelio De Rosa <aurelioderosa@gmail.com>
	     2  Batiste Bieler <batiste.bieler@gmail.com>
	     2  Benjamin Truyman <bentruyman@gmail.com>
	     2  Brian Brennan <me@brianlovesthings.com>
	     2  Chris Talkington <chris@talkingtontech.com>
	     2  Connor Atherton <c.liam.atherton@gmail.com>
	     2  Damian Janowski <damian.janowski@gmail.com>
	     2  Daniel Chatfield <chatfielddaniel@gmail.com>
	     2  Daniel Gálvez <dgalvez@editablething.com>
	     2  David Murdoch <david@davidmurdoch.com>
	     2  Dominik D. Geyer <dominik.geyer@gmail.com>
	     2  Gilad Peleg <giladp007@gmail.com>
	     2  Ismail Khair <ismail.khair@gmail.com>
	     2  Jason Moon <jmoon@socialcast.com>
	     2  Jess Thrysoee <jess@thrysoee.dk>
	     2  Joelle Fleurantin <joasqueeniebee@gmail.com>
	     2  Jonathan Sampson <jjdsampson@gmail.com>
	     2  Kris Borchers <kris.borchers@gmail.com>
	     2  Li Xudong <istonelee@gmail.com>
	     2  Liza Ramo <liza.h.ramo@gmail.com>
	     2  Manoj Kumar <nithmanoj@gmail.com>
	     2  Martin Naumann <martin@geekonaut.de>
	     2  Matt Farmer <matt@frmr.me>
	     2  Mike Sidorov <mikes.ekb@gmail.com>
	     2  Neeraj Singh <neerajdotname@gmail.com>
	     2  Rob Morgan <robbym@gmail.com>
	     2  Ryunosuke SATO <tricknotes.rs@gmail.com>
	     2  Sam Bisbee <sam@sbisbee.com>
	     2  Sebastian Burkhard <sebi.burkhard@gmail.com>
	     2  TJ VanToll <tj.vantoll@gmail.com>
	     2  Terry Jones <terry@jon.es>
	     2  Trey Hunner <treyhunner@gmail.com>
	     2  Uri Gilad <antishok@gmail.com>
	     2  Victor Homyakov <vkhomyackov@gmail.com>
	     2  nanto_vi <nanto@moon.email.ne.jp>
	     1  Adam Coulombe <me@adam.co>
	     1  Akintayo Akinwunmi <aakinwunmi@judge.com>
	     1  Alex Louden <alex@louden.com>
	     1  Alexander K <xpyro@ya.ru>
	     1  Alexander O'Mara <me@alexomara.com>
	     1  Alexis Abril <me@alexisabril.com>
	     1  Allen J Schmidt Jr <cobrasoft@gmail.com>
	     1  Amit Merchant <bullredeyes@gmail.com>
	     1  Andrea Giammarchi <andrea.giammarchi@gmail.com>
	     1  Andreas Solleder <asol@num42.de>
	     1  Andrew E Monat <amonat@gmail.com>
	     1  Andrew Plummer <plummer.andrew@gmail.com>
	     1  Anne-Gaelle Colom <coloma@westminster.ac.uk>
	     1  Anton Kovalyov <anton@kovalyov.net>
	     1  Arthur Stolyar <nekr.fabula@gmail.com>
	     1  Bastian Buchholz <buchholz.bastian@googlemail.com>
	     1  Ben Toews <mastahyeti@gmail.com>
	     1  Benjy Cui <benjytrys@gmail.com>
	     1  Bennett Sorbo <bsorbo@gmail.com>
	     1  Berker Peksag <berker.peksag@gmail.com>
	     1  Bernhard M. Wiedemann <jquerybmw@lsmod.de>
	     1  Bert Zhang <enbo@users.noreply.github.com>
	     1  Bin Xin <rhyzix@gmail.com>
	     1  Boom Lee <teabyii@gmail.com>
	     1  Brandon Sterne <bsterne@mozilla.com>
	     1  Bruno Pérel <brunoperel@gmail.com>
	     1  CDAGaming <cstack2011@yahoo.com>
	     1  Callum Macrae <callum@lynxphp.com>
	     1  Calvin Metcalf <calvin.metcalf@gmail.com>
	     1  Carl Danley <carldanley@gmail.com>
	     1  Chad Killingsworth <chadkillingsworth@missouristate.edu>
	     1  Chris Faulkner <thefaulkner@gmail.com>
	     1  Chris Price <price.c@gmail.com>
	     1  Chris Rebert <github@rebertia.com>
	     1  Christian Grete <webmaster@christiangrete.com>
	     1  Christian Kosmowski <ksmwsk@gmail.com>
	     1  Christophe Tafani-Dereeper <christophetd@hotmail.fr>
	     1  Christopher Jones <chris@cjqed.com>
	     1  Damian Senn <jquery@topaxi.codes>
	     1  Dan Hart <danhart@notonthehighstreet.com>
	     1  Daniel Husar <dano.husar@gmail.com>
	     1  Daniel Nill <daniellnill@gmail.com>
	     1  Daniel Pihlstrom <sciolist.se@gmail.com>
	     1  Danil Somsikov <danilasomsikov@gmail.com>
	     1  Dave Riddle <david@joyvuu.com>
	     1  David Benjamin <davidben@mit.edu>
	     1  David Bonner <dbonner@cogolabs.com>
	     1  David Broder-Rodgers <broder93@gmail.com>
	     1  David Corbacho <davidcorbacho@gmail.com>
	     1  David Fox <dfoxinator@gmail.com>
	     1  David Hong <d.hong@me.com>
	     1  Denis Knauf <Denis.Knauf@gmail.com>
	     1  Devin Cooper <cooper.semantics@gmail.com>
	     1  Devin Wilson <dwilson6.github@gmail.com>
	     1  Digitalxero <digitalxero>
	     1  Dmitry Gusev <dmitry.gusev@gmail.com>
	     1  Earle Castledine <mrspeaker@gmail.com>
	     1  Ed S <ejsanders@gmail.com>
	     1  Eddie Monge <eddie@eddiemonge.com>
	     1  Erik Lax <erik@datahack.se>
	     1  Felipe Sateler <fsateler@gmail.com>
	     1  Filipe Fortes <filipe@fortes.com>
	     1  Forbes Lindesay <forbes@lindesay.co.uk>
	     1  Frederic Hemberger <mail@frederic-hemberger.de>
	     1  Gabriel Schulhof <gabriel.schulhof@intel.com>
	     1  Gary Ye <garysye@gmail.com>
	     1  George Kats <katsgeorgeek@gmail.com>
	     1  George Mauer <gmauer@gmail.com>
	     1  Gilmore Davidson <gilmoreorless@gmail.com>
	     1  Greg Hazel <ghazel@gmail.com>
	     1  Greg Lavallee <greglavallee@wapolabs.com>
	     1  Guy Bedford <guybedford@gmail.com>
	     1  Henry Wong <henryw4k@gmail.com>
	     1  Henry Zhu <hi@henryzoo.com>
	     1  Heungsub Lee <h@subl.ee>
	     1  Ilya Kantor <iliakan@gmail.com>
	     1  Isaac Z. Schlueter <i@izs.me>
	     1  J. Ryan Stinnett <jryans@gmail.com>
	     1  Jacob Thornton <jacobthornton@gmail.com>
	     1  Jacob Wright <jacwright@gmail.com>
	     1  Jae Sung Park <alberto.park@gmail.com>
	     1  Jakob Stoeck <jakob@pokermania.de>
	     1  James Padolsey <cla@padolsey.net>
	     1  Jared Grippe <jared@deadlyicon.com>
	     1  Jason Merino <jasonmerino@gmail.com>
	     1  Jean Boussier <jean.boussier@gmail.com>
	     1  Jeffery To <jeffery.to@gmail.com>
	     1  Jeremy Dunck <jdunck@gmail.com>
	     1  Jha Naman <createnaman@gmail.com>
	     1  Joao Henrique de Andrade Bruni <joaohbruni@yahoo.com.br>
	     1  Joe Presbrey <presbrey@gmail.com>
	     1  Joe Trumbull <trumbull.j@gmail.com>
	     1  John Firebaugh <john_firebaugh@bigfix.com>
	     1  John Hoven <hovenj@gmail.com>
	     1  John Paul <john@johnkpaul.com>
	     1  Jon Dufresne <jon.dufresne@gmail.com>
	     1  Jon Evans <jon@springyweb.com>
	     1  Jon Hester <jon.d.hester@gmail.com>
	     1  Jonas Pfenniger <jonas@pfenniger.name>
	     1  Jordan Beland <jordan.beland@gmail.com>
	     1  Josh Soref <apache@soref.com>
	     1  Josh Varner <josh.varner@gmail.com>
	     1  Julian Alexander Murillo <julian.alexander.murillo@gmail.com>
	     1  Jun Sun <klsforever@gmail.com>
	     1  Justin <drakefjustin@gmail.com>
	     1  Karl Sieburg <ksieburg@yahoo.com>
	     1  Kim Dalsgaard <kim@kimdalsgaard.com>
	     1  Kyle Robinson Young <kyle@dontkry.com>
	     1  Lee Carpenter <elcarpie@gmail.com>
	     1  Leonardo Balter <leonardo.balter@gmail.com>
	     1  Liang Peng <poppinlp@gmail.com>
	     1  Lihan Li <frankieteardrop@gmail.com>
	     1  Luis Emilio Velasco Sanchez <emibloque@gmail.com>
	     1  MORGAN <morgan@morgangraphics.com>
	     1  Marcel Greter <marcel.greter@ocbnet.ch>
	     1  Marek Lewandowski <m.lewandowski@cksource.com>
	     1  Marian Sollmann <marian.sollmann@cargomedia.ch>
	     1  Mark Gibson <jollytoad@gmail.com>
	     1  Mark Raddatz <mraddatz@gmail.com>
	     1  Markus Staab <markus.staab@redaxo.de>
	     1  Martijn W. van der Lee <martijn@vanderlee.com>
	     1  Matan Kotler-Berkowitz <205matan@gmail.com>
	     1  Matt Curry <matt@pseudocoder.com>
	     1  Matt Mueller <mattmuelle@gmail.com>
	     1  Matthias Jäggli <matthias.jaeggli@gmail.com>
	     1  Michael Monteleone <michael@michaelmonteleone.net>
	     1  Michael Murray <m@murz.net>
	     1  Mike Pennisi <mike@mikepennisi.com>
	     1  Mike Petrovich <michael.c.petrovich@gmail.com>
	     1  Mu Haibao <mhbseal@163.com>
	     1  Nazar Mokrynskyi <nazar@mokrynskyi.com>
	     1  Nicolas HENRY <icewil@gmail.com>
	     1  Nikita Govorov <nikita.govorov@gmail.com>
	     1  Nilton Cesar <niltoncms@gmail.com>
	     1  Noah Sloan <noah.sloan@gmail.com>
	     1  Nowres Rafid <nowres.rafed@gmail.com>
	     1  Oskari <admin@o-programs.com>
	     1  Pascal Borreli <pascal@borreli.com>
	     1  Paul Mclanahan <pmclanahan@gmail.com>
	     1  Philip Jägenstedt <philip@foolip.org>
	     1  Pierre Spring <pierre@nelm.io>
	     1  Pinhook <contact@pinhooklabs.com>
	     1  Rafaël Blais Masson <rafbmasson@gmail.com>
	     1  Ralin Chimev <ralin.chimev@gmail.com>
	     1  Ralph Whitbeck <ralph.whitbeck@gmail.com>
	     1  Reed Loden <reed@reedloden.com>
	     1  Renato Oliveira dos Santos <ros3@cin.ufpe.br>
	     1  Rich Dougherty <rich@rd.gen.nz>
	     1  Richard Kraaijenhagen <stdin+git@riichard.com>
	     1  Richard McDaniel <rm0026@uah.edu>
	     1  Rod Vagg <rod@vagg.org>
	     1  Rodrigo Rosenfeld Rosas <rr.rosas@gmail.com>
	     1  Roland Eckl <eckl.roland@googlemail.com>
	     1  Roman Reiß <me@silverwind.io>
	     1  Ron Otten <r.j.g.otten@gmail.com>
	     1  Ronny Springer <springer.ronny@gmail.com>
	     1  Russell Holbrook <russell.holbrook@patch.com>
	     1  Ryan W Tenney <ryan@10e.us>
	     1  S. Andrew Sheppard <andrew@wq.io>
	     1  Sahab Yazdani <sahab.yazdani+github@gmail.com>
	     1  Schalk Neethling <schalk@ossreleasefeed.com>
	     1  Scott Hughes <hi@scott-hughes.me>
	     1  Sean Henderson <seanh.za@gmail.com>
	     1  Senya Pugach <upisfree@outlook.com>
	     1  Shashanka Nataraj <shashankan.10@gmail.com>
	     1  Shi Chuan <shichuanr@gmail.com>
	     1  Shivaji Varma <contact@shivajivarma.com>
	     1  Steen Nielsen <swinedk@gmail.com>
	     1  Stephen Edgar <stephen@netweb.com.au>
	     1  Steven Benner <admin@stevenbenner.com>
	     1  Sylvester Keil <sylvester@keil.or.at>
	     1  TJ Holowaychuk <tj@vision-media.ca>
	     1  Toby Brain <tobyb@freshview.com>
	     1  Todor Prikumov <tono_pr@abv.bg>
	     1  Tom H Fuertes <TomFuertes@gmail.com>
	     1  Tom H Fuertes <tomfuertes@gmail.com>
	     1  Tom Viner <github@viner.tv>
	     1  Veaceslav Grimalschi <grimalschi@yandex.ru>
	     1  Vitaliy Terziev <vitaliyterziev@gmail.com>
	     1  Vladimir Zhuravlev <private.face@gmail.com>
	     1  Vladislav Zarakovsky <vlad.zar@gmail.com>
	     1  Wesley Walser <waw325@gmail.com>
	     1  William Robinet <william.robinet@conostix.com>
	     1  Winston Howes <winstonhowes@gmail.com>
	     1  Xavier Montillet <xavierm02.net@gmail.com>
	     1  Yiming He <yiminghe@gmail.com>
	     1  Yongwoo Jeon <yongwoo.jeon@navercorp.com>
	     1  Zachary Adam Kaplan <razic@viralkitty.com>
	     1  Zack Hall <zackhall@outlook.com>
	     1  avaly <github-com@agachi.name>
	     1  basil.belokon <basil.belokon@gmail.com>
	     1  cmc3cn <59194618@qq.com>
	     1  karan-96 <karanbatra96@gmail.com>
	     1  nanto <nanto@moon.email.ne.jp>
	     1  njhamann <njhamann@gmail.com>
	     1  ros3cin <ros3@cin.ufpe.br>
	     1  temp01 <temp01irc@gmail.com>
	     1  tmybr11 <tomas.perone@gmail.com>
	     1  tsinha <tsinha@Anthonys-MacBook-Pro.local>
	     1  unknown <Igen005@.upcorp.ad.uprr.com>
	     1  南漂一卒 <shiy007@qq.com>
25. No repositório jqueryrepo, qual o efeito de git remote -v?
	$ git remote -v
	origin  https://github.com/jquery/jquery.git (fetch)
	origin  https://github.com/jquery/jquery.git (push)



*/
