# Componentes Dinâmicos

As vezes é utuil altenar dinamicamente entre os componentes.
Fazer isso é possivel devido ao elemento  component do vue com o atributo especial is.

![image](https://user-images.githubusercontent.com/64383080/158844205-385c7142-b06d-4088-8271-44784a5d425b.png)

ou seja, um componente pode ter varias estancias

![image](https://user-images.githubusercontent.com/64383080/158846573-09f6ee50-cca8-4568-acb3-f8f37547bf48.png)

![image](https://user-images.githubusercontent.com/64383080/158847631-78a3ed86-6fed-4b23-9434-e8150dd0547a.png)

![image](https://user-images.githubusercontent.com/64383080/158847697-32596c61-f7cb-4437-9576-fb11fb730192.png)

![image](https://user-images.githubusercontent.com/64383080/158847767-0d0013de-12a1-4c0b-9d7d-5d6440e6aadc.png)


A melhor combinação é usar SFC e componentes locais quando usando algum sistema de modulos, como no exemplo projeto criado com vue-cli

![image](https://user-images.githubusercontent.com/64383080/158848082-1cf5536b-503c-418f-ac74-ea4063a3186e.png)


![image](https://user-images.githubusercontent.com/64383080/158875416-19f8406b-424b-4a18-8254-6668491fb0a0.png)


![image](https://user-images.githubusercontent.com/64383080/158875687-28d3182f-697c-49ef-911d-5818ae81d538.png)


![image](https://user-images.githubusercontent.com/64383080/158876371-5ed4f093-1973-42e2-879c-f31df48b4359.png)

![image](https://user-images.githubusercontent.com/64383080/158876719-9ef1b385-4fa5-4ce8-83c7-9d19ba89aa99.png)

Caso o slot não tenha nome implicitamente tem o nome de defoult.

A diretiva usada para referencia do slot é o v-slot e sua abreviação é o # joguinho da velha. 

# Provide / inject

Quando precisamos passar os dados do componente pai para o filho usamos o props.
Imagine a estrutura que tem alguns componentes aninhados  e precise de algo do pai para o componente filho que tambem esta aninhado. Tera que passar por toda essa estrutura o props o que pode gerar incomodos. 

Nesses casos podemos usar o par provide e inject. Os componentes pai podem servir como provedor de dependencia para todos os seus filhos, independente da profundidade da hierarquia do componente.
É como se o pai estivendo provendo o dado ou informação para o filho

![image](https://user-images.githubusercontent.com/64383080/158878454-dd5ed2b4-8015-4c50-9c01-77d22d1e4291.png)

Exercicio com provide

![image](https://user-images.githubusercontent.com/64383080/158879923-f3dfeec7-01de-4cf8-be73-bfcab27b776f.png)
