

# Transfer Learning com YOLO e Open Images Dataset V7

## Descrição do Projeto

Este projeto tem como objetivo realizar um *Transfer Learning* utilizando o modelo *YOLO* (You Only Look Once) em um subconjunto do *Open Images Dataset V7*. O *Transfer Learning* permite reutilizar modelos pré-treinados para tarefas específicas, reduzindo o tempo de treinamento e melhorando a precisão dos resultados.

---

## 1. Configuração do Ambiente

Antes de iniciar o código, é importante configurar o ambiente no Google Colab para utilizar uma GPU. Isso acelera significativamente o processamento dos dados e o treinamento do modelo.

```python
# Verificando se a GPU foi inicializada
import tensorflow as tf
device_name = tf.test.gpu_device_name()
print(device_name)
```

Saída esperada:
```
/device:GPU:0
```

Caso a GPU não esteja ativada, é necessário configurar o Colab acessando: **Ambiente de Execução > Alterar Tipo de Hardware > GPU**.

---

## 2. Sobre o Open Images Dataset V7

O *Open Images Dataset V7* é um extenso conjunto de dados para reconhecimento de imagens e detecção de objetos. Algumas de suas características incluem:

- **15.851.536** caixas delimitadoras em **600** classes
- **2.785.498** segmentações de instância em **350** classes
- **3.284.280** anotações de relacionamento
- **66.391.027** anotações de ponto em **5827** classes
- **61.404.966** rótulos de nível de imagem em **20638** classes
- **478.000** imagens de crowdsourcing com mais de **6000** classes

Devido ao alto volume de imagens e classes, será selecionada apenas uma classe e um número limitado de imagens.

[Site Oficial: Open Images Dataset V7](https://storage.googleapis.com/openimages/web/index.html)

---

## 3. Importando e Preparando os Dados

Para baixar e manipular as imagens, utilizaremos o repositório *OIDv6 ToolKit*, que permite baixar imagens do Open Images Dataset e convertê-las para o formato YOLO.

### 3.1 Clonando o Repositório
```bash
!git clone https://github.com/NanoCode012/OIDv6_ToolKit_Download_Open_Images_Support_Yolo_Format.git
```

### 3.2 Instalando as Dependências
```bash
!pip3 install -r /content/OIDv6_ToolKit_Download_Open_Images_Support_Yolo_Format/requirements.txt
```

Esse toolkit permite fazer o download de imagens e anotações do Open Images Dataset e convertê-las para o formato YOLO, facilitando o treinamento de modelos de detecção de objetos.

---

## 4. Executando o Treinamento com YOLO

Os próximos passos envolvem:
1. Selecionar a classe desejada para download.
2. Baixar as imagens e suas respectivas anotações.
3. Preparar os arquivos no formato YOLO.
4. Treinar o modelo YOLO com os dados customizados.

---

## 5. Contribuição

Se você deseja contribuir para este projeto, siga estas etapas:
1. **Fork** o repositório
2. Crie uma nova *branch*: `git checkout -b minha-feature`
3. Commit suas modificações: `git commit -m 'Adicionando nova funcionalidade'`
4. Envie para o branch principal: `git push origin minha-feature`
5. Abra um **Pull Request**

---

## 6. Licença

Este projeto está sob a licença **MIT** - veja o arquivo [LICENSE](LICENSE) para mais detalhes.

