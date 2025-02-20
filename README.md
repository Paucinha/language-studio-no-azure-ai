# Análise de Sentimentos com Language Studio no Azure AI

![GitHub](https://img.shields.io/github/license/Paucinha/api-ecommerce-dio?style=flat-square)

Neste LAB, exploraremos o uso do Azure Speech Studio e a análise linguística proporcionada pelo Language Studio. Durante a prática, teremos a oportunidade de aprofundar nosso entendimento sobre como aproveitar essas ferramentas avançadas da Microsoft Azure. Estaremos focados em aprimorar nossas habilidades na implementação de soluções de análise de fala e linguagem, abrindo portas para uma compreensão mais ampla e prática das capacidades oferecidas por essas tecnologias inovadoras.

**Inteligência Artificial (IA) | Full-Stack | Básico**

#### Criar um recurso de idioma

Você pode usar muitos recursos de Linguagem do Azure AI com um recurso **de Linguagem** ou **de serviços do Azure AI**. Há algumas instâncias em que apenas um recurso de Linguagem pode ser usado. Para o exercício abaixo, usaremos um recurso **de Linguagem**. Se você ainda não fez isso, crie um recurso **de Linguagem na sua assinatura do Azure.

1 - Em outra aba do navegador, abra o [**portal do Azure**](https://portal.azure.com), entrando com a conta da Microsoft associada à sua assinatura do Azure.

2 - Clique no botão **＋Criar um recurso** e pesquise por Serviço de idioma. Selecione **criar** um plano de **serviço de idioma**. Você será levado para uma página para **Selecionar recursos adicionais**. Mantenha a seleção padrão e clique em **Continuar para criar seu recurso**.

3 - Na página **Criar idioma**, configure-o com as seguintes configurações:

- **Assinatura:** sua assinatura do Azure .
- **Grupo de recursos:** selecione ou crie um grupo de recursos com um nome exclusivo.
- **Região:** Selecione a região geográfica mais próxima. Se estiver no leste dos EUA, use “East US 2”.
- **Nome:** Insira um nome exclusivo.
- **Nível de preço:** Free F0 ou S se Free F0 não estiver disponível.
- **Ao marcar esta caixa, reconheço que li e compreendi todos os termos abaixo:** Selecionado.
  
4 - Selecione **Revisar + criar** e depois **Criar** e aguarde a conclusão da implantação.

```json
{
    "id": "/subscriptions/f5f6088e-679a-4fc3-9a5d-600dcca616e6/resourceGroups/AZ-900_Lab_DIO/providers/Microsoft.CognitiveServices/accounts/idiomalabdio",
    "name": "idiomalabdio",
    "type": "Microsoft.CognitiveServices/accounts",
    "etag": "\"68002201-0000-0100-0000-67b782cc0000\"",
    "location": "eastus",
    "sku": {
        "name": "F0"
    },
    "kind": "TextAnalytics",
    "tags": {},
    "properties": {
        "endpoint": "https://idiomalabdio.cognitiveservices.azure.com/",
        "internalId": "586e960413e14b2d9bf7f1c63dac7229",
        "dateCreated": "2025-02-20T19:29:44.703353Z",
        "apiProperties": {
            "qnaAzureSearchEndpointKey": null
        },
        "quotaLimit": {
            "rules": [
                {
                    "key": "workflow.endpoint.postcalls",
                    "renewalPeriod": 2592000,
                    "count": 5000,
                    "matchPatterns": [
                        {
                            "path": "/language/:analyze-conversations",
                            "method": "*"
                        }
                    ]
                }
            ]
        },
        "isMigrated": false,
        "customSubDomainName": "idiomalabdio",
        "networkAcls": {
            "defaultAction": "Allow",
            "virtualNetworkRules": [],
            "ipRules": []
        },
        "privateEndpointConnections": [],
        "publicNetworkAccess": "Enabled",
        "capabilities": [
            {
                "name": "VirtualNetworks"
            },
            {
                "name": "CustomerManagedKey"
            },
            {
                "name": "CustomerManagedStorage"
            },
            {
                "name": "Cloud",
                "value": "TextAnalytics.Healthcare,TextAnalytics.Analyze,QuestionAnswer.AllApis,LanguageService.QuestionAnsweringApis"
            },
            {
                "name": "Container",
                "value": "TextAnalytics.Healthcare,TextAnalytics.EntityV3,TextAnalytics.EntityONNX,TextAnalytics.Keyphrase,TextAnalytics.KeyphraseV2,TextAnalytics.KeyPhraseONNX,TextAnalytics.LanguageFastText,TextAnalytics.Language,TextAnalytics.LanguageV2,TextAnalytics.Sentiment,TextAnalytics.SentimentV2,TextAnalytics.SentimentV3,TextAnalytics.SentimentV3Preview,TextAnalytics.SentimentONNX,TextAnalytics.CustomNER,TextAnalytics.textanalyticsdispatcher,TextAnalytics.SummarizationFrontend,TextAnalytics.SummarizationWorker,TextAnalytics.PII,TextAnalytics.CluRuntime,TextAnalytics.NER"
            }
        ],
        "endpoints": {
            "Text Analytics": "https://idiomalabdio.cognitiveservices.azure.com/",
            "Custom Text Authoring": "https://idiomalabdio.cognitiveservices.azure.com/",
            "Conversational Language Understanding Authoring": "https://idiomalabdio.cognitiveservices.azure.com/",
            "Custom Question Answering Authoring": "https://idiomalabdio.cognitiveservices.azure.com/",
            "Custom Question Answering": "https://idiomalabdio.cognitiveservices.azure.com/",
            "ConversationalLURuntime": "https://idiomalabdio.cognitiveservices.azure.com/",
            "Language": "https://idiomalabdio.cognitiveservices.azure.com/",
            "QnAMaker": "https://idiomalabdio.cognitiveservices.azure.com/",
            "Turing": "https://idiomalabdio.cognitiveservices.azure.com/",
            "QuestionAnswering": "https://idiomalabdio.cognitiveservices.azure.com/",
            "LUIS": "https://idiomalabdio.cognitiveservices.azure.com/",
            "Container": "https://idiomalabdio.cognitiveservices.azure.com/"
        },
        "provisioningState": "Succeeded"
    },
    "identity": {
        "principalId": "81a76598-00ae-4582-8920-001d3c4bd58a",
        "tenantId": "d2da6806-596c-4c79-bc66-2f3fc595a29c",
        "type": "SystemAssigned"
    },
    "systemData": {
        "createdBy": "paucia.renan@gmail.com",
        "createdByType": "User",
        "createdAt": "2025-02-20T19:29:43.1679772Z",
        "lastModifiedBy": "paucia.renan@gmail.com",
        "lastModifiedByType": "User",
        "lastModifiedAt": "2025-02-20T19:29:43.1679772Z"
    },
    "apiVersion": "2021-04-30"
}
```

#### Configure seu recurso no Azure AI Language Studio

1 - Em outra aba do navegador, abra o [**Language Studio**](https://language.cognitive.azure.com) e faça login.

2 - Quando solicitado a selecionar um recurso do Azure , faça as seguintes configurações:

- **Diretório do Azure:** Diretório padrão, o diretório que você está usando
- **Assinatura do Azure:** Selecione a assinatura que você está usando
- **Tipo de recurso:** Idioma
- **Nome do recurso:** selecione o recurso de serviço de idioma que você acabou de criar
  
Em seguida, selecione **Concluído**.

#### Analisar avaliações no Language Studio

1 - Em um navegador da Web, navegue até o [**Language Studio**](https://language.cognitive.azure.com).

2 - Na página inicial **Bem-vindo ao Language Studio**, selecione a aba **Classificar texto** e depois selecione o bloco **Analisar sentimento e extrair opiniões**7 .

3 - Em Selecionar (*)idioma do texto(*), selecione **Inglês**.

4 - Em Selecione (*)seu recurso do Azure(*), selecione seu recurso.

5 - Em (*)Insira seu próprio texto, carregue um arquivo ou use um de nossos textos de exemplo(*), copie e cole a seguinte análise:

```código
 Tired hotel with poor service
 The Royal Hotel, London, United Kingdom
 5/6/2018
 This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
```

6 - Marque a caixa para confirmar que a demonstração incorrerá em uso e poderá incorrer em custos e, em seguida, selecione **Executar**.

7 - Revise a saída. Observe que o (*)documento(*) é analisado quanto ao sentimento, assim como cada (*)frase(*). Selecione **Frase** 1 para mostrar a análise de sentimento para essa frase.

Observe que há um sentimento geral seguido por pontuações ao lado de três categorias, (*)pontuação positiva(*), (*)pontuação neutra(*), (*)pontuação negativa(*). Em cada uma das categorias, uma pontuação entre 0 e 1 é fornecida. Essas pontuações de confiança indicam a probabilidade de o texto fornecido ser um sentimento específico.

Selecione **Frase** 1 novamente para fechar.

1 - Role para cima para selecionar **Limpar caixa de texto** e copie e cole a seguinte revisão:

```código
 Good Hotel and staff
 The Royal Hotel, London, UK
 3/2/2018
 Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
```

2 - Selecione **Executar** . Revise a saída e revise o sentimento e o nível de confiança.

3 - Selecione **Limpar** caixa de texto novamente e copie e cole a seguinte revisão:

![Limpar](https://img.shields.io/github/license/Paucinha/api-ecommerce-dio?style=flat-square)





4 - Selecione **Run** e revise o sentimento junto com o nível de confiança. Dê uma olhada no texto e compare-o com a análise de sentimento que o serviço retornou.

Neste exercício, você usou o Language Studio para criar um novo recurso de idioma ou usar um recurso de idioma existente. Você habilitou o recurso em Configurações antes de experimentar o serviço de mineração de opinião e sentimento. Em seguida, você testou o serviço com três partes de texto.

#### Limpar

Se você não pretende fazer mais exercícios, exclua quaisquer recursos que não precise mais. Isso evita acumular custos desnecessários.

1 - Abra o [**portal do Azure**](https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
2 - Selecione o recurso e selecione **Delete** e depois **Yes** para confirmar. O recurso é então excluído.

#### Saber mais

Para saber mais sobre o que você pode fazer com este serviço, consulte a [página Serviço de idiomas](https://learn.microsoft.com/pt-br/azure/ai-services/language-service/overview).

[**Fonte**](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/06-text-analysis.html)

##

Projeto desenvolvido durante o [**Bootcamp Bradesco - Java Cloud Native**](https://www.dio.me/bootcamp/bradesco-java-cloud-native), fornecido pela [**DIO**](https://www.dio.me/)

##

- [By Páucinha](https://github.com/Paucinha)
