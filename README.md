# my-vue-app

## Project setup
```
npm install
```

### Compiles e hot-reloads para desenvolvimento
```
npm run serve
```

### Compiles e minifies para produção
```
npm run build
```

### Arquivos lints e fixes
```
npm run lint
```

### Alterar configurações
See [Configuration Reference](https://cli.vuejs.org/config/).

### Instalar o chart:
```
npm install vue-chartjs chart.js
```

# Hora de praticar - siga os passos abaixo para plotar um gráfico usando o Vue:
1°- Abra o replit no seu navegador: https://replit.com/

2°- No canto superior direito clique em 'Create Repl', busque por 'VueJs' e crie seu projeto

3°- Clique na aba 'Shell' ao lado da aba 'Console' e digite o comando: npm install vue-chartjs chart.js

4°- Crie um componente dentro da pasta 'components' com o nome de 'BarCharts.vue'

5°- Vá até o site vue-charts e copie o template 'BarChart.vue': https://vue-chartjs.org/guide/#creating-your-first-chart

6°- Cole o template copiado dentro do componente 'BarCharts.vue' que você criou

7°- Dentro do componente 'App.vue' dentro da tag 'script' adicione a importação do Barchat: import BarChart from './components/BarChart.vue'

8°- Apague as importações de 'Helloworld' e 'TheWelcome'. Apague também a tag 'header' e 'style'. Mantenha a tag 'template' apenas com a 'main' dentro

9°- Ainda dentro do 'App.vue' dentro da 'main' adicione: <BarChart /> e apague <TheWelcome />

10°- Vá até a pasta 'assents' e delete o conteúdo do arquivo 'main.css'

11°- Agora é só clicar em 'run' e se divertir editando o gráfico modelo barra


