--- 
title: "Criar configurações para avaliar a entrada de documentos para atualizações de dados de aplicativos (ER)"
description: "Este procedimento mostra como criar configurações de ER (relatório eletrônico) para analisar um documento eletrônico."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: 96c9397c6a83d61b679492f66f4aa6661f1f8621
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="design-configurations-to-parse-incoming-documents-for-application-data-updates-er"></a>Criar configurações para avaliar a entrada de documentos para atualizações de dados de aplicativos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar configurações de ER (relatório eletrônico) para analisar um documento eletrônico. Nesse procedimento, você importará as configurações de ER necessárias que foram criadas para a empresa exemplo, Litware, Inc., e irá usá-las para analisar a entrada de documentos eletrônicos. Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, "ER Criar um provedor de configuração e marcá-lo como ativo".

Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico. 

Estas etapas podem ser concluídas usando qualquer conjunto de dados. Antes de começar, baixe e salve os arquivos listados no tópico da Ajuda, "Analisar documentos de entrada para atualizar os dados do aplicativo" (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/parse-incoming-electronic-documents). Os arquivos são: EFSTA model.xml, EFSTA format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo. Se não visualizar esse provedor de configuração, conclua as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.  
2. Clique em Configurações de relatórios.
    * O cenário a seguir será usado para mostrar os recursos de análise de documentos eletrônicos de entrada no formato XML: o aplicativo ERP (Dynamics 365 for Finance and Operations) solicita dados do serviço Web (como o serviço fiscal EFSTA http://efsta.org/) e analisa as respostas de entrada para atualizar os dados do aplicativo adequadamente. Para a maneira mais eficiente de analisar, um único formato de ER é usado apesar da estrutura diferente dos documentos de entrada esperados em formato XML.   

## <a name="import-and-review-er-configurations"></a>Importar e examinar configurações de ER
Importe a configuração de modelo de ER que contém o modelo de dados de exemplo criado para armazenar os detalhes do arquivo de entrada.  
1. Clique em Trocar.
2. Clique em Carregar de um arquivo XML.
    * Clique em Procurar e selecione o arquivo EFSTA model.xml.  
3. Clique em OK.
4. Na árvore, selecione 'Modelo EFSTA'.
5. Clique em Designer.
    * Revise a estrutura do modelo de dados importado. Observe que a enumeração enumType é definida para reconhecer os seguintes tipos de respostas de serviço: para obter a confirmação sobre o envio da transação, obter informações sobre a última transação enviada e reconhecer os tipos de resposta sem suporte.   
6. Na árvore, expanda 'Resposta'.
    * Observe que o item raiz 'Resposta' é definido para especificar que tipo de dados deve ser obtido de uma resposta de serviço com suporte para atualizar os dados do aplicativo adequadamente.   
7. Feche a página.
    * Você importará a configuração de formato de ER que especifica como os documentos de entrada serão analisados para armazenar dados no modelo de dados de ER.   
8. Clique em Trocar.
9. Clique em Carregar de um arquivo XML.
    * Clique em Procurar e selecione o arquivo EFSTA format.xml.  
10. Clique em OK.
11. Na árvore, expanda 'Modelo EFSTA'.
12. Na árvore, selecione 'Modelo EFSTA\Formato EFSTA'.
13. Clique em Designer.
14. Clique em Expandir/recolher.
    * Observe que o elemento de formato CASE é usado como a raiz e contém três elementos FILE aninhados, o que significa que esse formato foi criado para analisar arquivos de entrada de vários formatos.  
15. Na árvore, selecione 'Respostas\Conclusão de transação\TraC'.
    * Observe que a resposta sobre a transação enviada parte do elemento raiz 'TraC'.   
16. Na árvore, selecione 'Respostas\Última solicitação de transação\Tra'.
    * Observe que a resposta sobre a última transação enviada parte do elemento raiz 'Tra'.   
17. Na árvore, selecione 'Respostas\Resposta inesperada\Texto'.
    * O terceiro elemento FILE com elemento TEXT aninhado foi adicionado para reconhecer quaisquer outros tipos de respostas que sejam diferentes dos mencionados acima.   
18. Clique em Mapear formato para modelo.
    * Esse mapeamento de modelo contém a definição do fluxo de dados para armazenar detalhes do documento de entrada analisado com o uso dos itens do modelo de dados.  
19. Clique em Designer.
20. Na árvore, expanda 'format'.
21. Na árvore, expanda “formato\Respostas: Caso(Responses)'.
    * Examine a estrutura da fonte de dados de ‘formato’. Observe que os três tipos de resposta são oferecidos separadamente.   
22. Na árvore, selecione “formato\Respostas: Caso(Responses)\aType'.
    * O item da fonte de dados 'aType' foi adicionado para indicar o tipo de resposta e está associado ao item do modelo de dados 'Tipo'.  
23. Clique na guia Validações.
24. Na árvore, selecione 'Tipo = format.Responses.aType'.
    * Observe que a validação de ER foi configurada para informar ao usuário sobre a situação quando a estrutura de resposta não corresponde à confirmação sobre o envio da transação ou às informações sobre a última transação enviada (caso de resposta sem suporte).   
25. Feche a página.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Executar mapeamento de modelo de formato de ER configurado para analisar arquivos de entrada
Você executará o mapeamento de modelo criado para fins de teste para ver como o formato de ER configurado analisará respostas de serviços de entrada. Esta etapa usa diferentes arquivos XML para simular diferentes tipos de respostas de serviços Web.   
1. Abra o arquivo Response1.xml em um leitor xml, como um navegador da Web. Observe que esse arquivo contém detalhes de confirmação sobre a transação concluída (‘TraC’ é o elemento raiz).   
2. Clique em Executar.
    * Clique em Procurar e selecione o arquivo Response1.xml.  
3. Clique em OK.
    * Revise a saída gerada. Observe que o tipo de resposta foi corretamente reconhecido e analisado (ERModelEnumDataSourceHandler#EFSTA model#enumType#C significa caso de conclusão de transação).   
    * Abra o arquivo Response2.xml em um leitor XML. Observe que esse arquivo contém informações sobre a última transação enviada (‘Tra’ é o elemento raiz).   
4. Clique em Executar.
    * Clique em Procurar e selecione o arquivo Response2.xml.  
5. Clique em OK.
    * Revise a saída gerada. Observe que o tipo de resposta foi corretamente reconhecido e analisado (ERModelEnumDataSourceHandler#EFSTA model#enumType#R significa caso de reinicialização do sistema).   
    * Abra o arquivo Response3.xml em um leitor XML. Observe que esse arquivo parte do item raiz TraZ e que essa estrutura não é configurada usando o formato de ER.   
6. Clique em Executar.
    * Clique em Procurar e selecione o arquivo Response3.xml.  
7. Clique em OK.
    * Revise a saída gerada. Observe que o tipo de resposta foi corretamente reconhecido como sem suporte (ERModelEnumDataSourceHandler#EFSTA model#enumType#U). A mensagem correspondente foi colocada no Log de Informações (de acordo com a configuração de validação de ER) e a maior parte do modelo de dados não foi preenchida.   
    * Abra o arquivo Response4.xml em um leitor XML. Observe que a estrutura desse arquivo é praticamente igual à do arquivo analisado com êxito Response1.xml, exceto a sequência de elementos aninhados do elemento raiz 'TraC'.   
8. Clique em Executar.
    * Clique em Procurar e selecione o arquivo Response4.xml.  
9. Clique em OK.
    * Revise a saída gerada. Observe que o tipo de resposta foi corretamente reconhecido como sem suporte (ERModelEnumDataSourceHandler#EFSTA model#enumType#U). A mensagem correspondente foi colocada no Log de Informações e a maior parte do modelo de dados não foi preenchida. Isso é porque a configuração atual desse formato de ER pressupõe uma determinada sequência de elementos aninhados do item raiz do arquivo de entrada.   
10. Feche a página.
11. Na árvore, selecione 'Respostas\Conclusão de transação\TraC'.
12. No campo Ordem de análise de elementos aninhados, selecione 'Qualquer'.
    * Selecione Qualquer no campo 'Ordem de análise de elementos aninhados' para permitir qualquer sequência de elementos aninhados para este item XML raiz.  
13. Clique em Salvar.
14. Clique em Mapear formato para modelo.
15. Clique em Executar.
    * Clique em Procurar e selecione o arquivo Response4.xml.  
16. Clique em OK.
    * Revise a saída gerada. Observe que o tipo de resposta agora foi corretamente reconhecido como igual para o arquivo Response1.xml.  


