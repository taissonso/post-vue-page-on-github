<template>
  <main>
    <div class="left"></div>
    <article>
      <h2>Criando, separando e publicando seus projetos</h2>
      <p>Nesse passo a passo rápido vou mostrar como publicar seus projetos, separando as partes de desenvolvimento e produção 
        da forma mais simples possível. Assim deixando seu projeto não só no código [GitHub] mas também mostrando a parte visual [GitHub Pages] 
        sem que as pessoas tenham que baixar/instalar seus projetos.  
      </p>
      <p>Crie seu projeto VUE.js e altere conforme sua necessidade</p>

      <p>Crie seu repositório no <a href="https://github.com/" target="_blank" rel="noopener noreferrer">GitHub</a> e comiteo.</p>
      
      <p>[Atualização do GitHub]: o GitHub teve alterações no nome da branch padrão dos projetos, onde a branch raiz se chamava 
        "master" foi alterada para "main". Segundo a matéria para evitar referências à escravidão, a matéria pode ser lida 
        <a href="https://www.zdnet.com/article/github-to-replace-master-with-alternative-term-to-avoid-slavery-references/" target="_blank" 
        rel="noopener noreferrer">clicando aqui</a>
      </p>

      <p>Mas vamos ao que interessa, caso esteja com dificuldade em comitar na raiz do projeto siga os seguintes passos:</p>

      <p>$ git init</p>
      <p>$ git remote add origin "SSH KEY DO PROJETO</p>
      <p>$ git pull origin main</p>
      <span>Copiamos o contéudo do branch raiz para o repósitorio local.</span>
      <p>$ git branch -m master main</p>
      <span>Movemos o histórico do branch master para o novo branch main</span>
      <p>$ git add .</p>
      <p>$ git push --set-upstream origin main</p>
      <p>Assim acabamos de publicar a versão de desenvolvimento do seu projeto.</p>

      <h2>Instalando o gh-pages, construindo, preparando/publicando o projeto:</h2>
      <p>gh-pages irá criar uma branch chamada gh-pages e publicar o conteúdo da pasta 'dist' nessa branch e também já irá 
        publicar o projeto no GitHub Pages automaticamente.
      </p>
      <p>Instalação: abra o terminal de sua prefêrencia, entre na pasta do seu projeto e digite o seguinte comando:</p>
      <p>$ npm add --also=dev gh-pages</p>



      <p>Preparação: Na raiz do seu projeto crie um arquivo chamado "vue.config.js" e coloque o seguinte código</p>
      <code>
        module.exports = {<br>
          publicPath: '/nome do seu projeto no github'<br>
        }
      </code>
      <p>Por que fazer isso? para que o GitHub Pages saiba o caminho dos arquivos css, imagens, javascript e etc do seu projeto 
        em Produção.
      </p>

      <p>Construção/build do seu projeto:</p>
      <p>$ npm run build</p>

      <p>Publicação: o comando para o gh-pages criar e publicar no github pages.</p>
      <p>$ ./node_modules/.bin/gh-pages -d dist</p>

      <p>Pronto, seu projeto agora está online no GitHub Pages!!!</p>
    

      <h2>Criando um script para buildar e publicar o seu projeto</h2>
      <p>Entre no arquivo 'package.json', na parte de "script" crie o seguinte comando:</p>
      <p>"deploy": "npm run build && ./node_modules/.bin/gh-pages -d dist"
        <br>ou<br>
        "deploy": "npm run build && .\\node_modules\\.bin\\gh-pages -d dist"
      </p>

      <p>OBS: esse segundo comando com as barras invertidas pode acontecer, caso o npm não encontre o caminho da pasta 
        do gh-pages.</p>

      <p>Depois basta executar o comando:</p>
      <code>$ npm run deploy</code>

      <p>Este comando irá construir e publicar na branch criada pelo gh-pages e deixando seu projeto publicado e online.
        Assim temos como manter as duas versões desenvolvimento e produção do mesmo projeto e separados em branch's diferentes
        de uma forma simples e prática.</p>
    </article>
    <div class="right"></div>
  </main>
</template>

<script>
export default {
  name: 'Main',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>


main {
  background: chartreuse;
  width: 100vw;
  display: flex;
  flex-direction: row;
  flex-grow: 1;
}

article {
  width: 70vw;
  background: white;
}

.left, .right {
  width: 15vw;
  background: cyan;
}

</style>
