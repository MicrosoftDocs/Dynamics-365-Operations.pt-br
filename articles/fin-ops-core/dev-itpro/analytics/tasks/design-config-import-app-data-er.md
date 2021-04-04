---
title: Criar configurações ER para analisar documentos recebidos
description: Este procedimento mostra como criar configurações de ER (relatório eletrônico) para analisar um documento eletrônico.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7235d75aee3b8fdf39492cfbc1760bf6eae4b82e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562847"
---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>Criar configurações ER para analisar documentos recebidos

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar configurações de ER (relatório eletrônico) para analisar um documento eletrônico. Nesse procedimento, você importará as configurações de ER necessárias que foram criadas para a empresa exemplo, Litware, Inc., e irá usá-las para analisar a entrada de documentos eletrônicos. Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, "ER Criar um provedor de configuração e marcá-lo como ativo."

Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico.

Estas etapas podem ser concluídas usando qualquer conjunto de dados. Antes de começar, baixe e salve os arquivos listados no tópico, "Analisar documentos de entrada para atualizar os dados da solicitação de emprego" ([Analisar documentos recebidos](../parse-incoming-electronic-documents.md)). Os arquivos são: EFSTA model.xml, EFSTA format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo. Se não visualizar este provedor de configuração, conclua as etapas no procedimento "Criar um provedor de configuração e marcá-lo como ativo".
2. Selecione Configurações de relatórios.
    * O cenário a seguir será usado para mostrar os recursos de análise de documentos eletrônicos de entrada no formato XML: o aplicativo de ERP solicita dados do serviço Web (como o serviço fiscal [efsta](http://efsta.org/)) e analisa as respostas recebidas para atualizar os dados do aplicativo adequadamente. Para a maneira mais eficiente de analisar, um único formato de ER é usado apesar da estrutura diferente dos documentos de entrada esperados em formato XML.

## <a name="import-and-review-er-configurations"></a>Importar e examinar configurações de ER

Importe a configuração de modelo de ER que contém o modelo de dados de exemplo criado para armazenar os detalhes do arquivo de entrada.

1. Selecione Taxa de câmbio.
2. Selecione Carregar do arquivo XML.
    * Selecione Procurar e selecione o arquivo EFSTA model.xml.
3. Selecione OK.
4. Na árvore, selecione 'Modelo EFSTA'.
5. Selecione Designer.
    * Revise a estrutura do modelo de dados importado. A enumeração enumType é definida para reconhecer os seguintes tipos de respostas de serviço: para obter a confirmação sobre o envio da transação, obter informações sobre a última transação enviada e reconhecer os tipos de resposta sem suporte.
6. Na árvore, expanda 'Resposta'.
    * O item raiz "Resposta" é definido para especificar que tipo de dados deve ser obtido de uma resposta de serviço com suporte para atualizar os dados do aplicativo adequadamente.
7. Feche a página.
    * Você importará a configuração de formato de ER que especifica como os documentos de entrada serão analisados para armazenar dados no modelo de dados de ER.
8. Selecione Taxa de câmbio.
9. Selecione Carregar do arquivo XML.
    * Selecione Procurar e selecione o arquivo EFSTA format.xml.
10. Selecione OK.
11. Na árvore, expanda 'Modelo EFSTA'.
12. Na árvore, selecione 'Modelo EFSTA\Formato EFSTA'.
13. Selecione Designer.
14. Selecione Expandir/Recolher.
    * O elemento de formato CASE é usado como a raiz e contém três elementos FILE aninhados, o que significa que esse formato foi criado para analisar arquivos de entrada de vários formatos.
15. Na árvore, selecione 'Respostas\Conclusão de transação\TraC'.
    * A resposta sobre a transação enviada parte do elemento raiz "TraC".
16. Na árvore, selecione 'Respostas\Última solicitação de transação\Tra'.
    * A resposta sobre a última transação enviada parte do elemento raiz "Era".
17. Na árvore, selecione 'Respostas\Resposta inesperada\Texto'.
    * O terceiro elemento FILE com elemento TEXT aninhado foi adicionado para reconhecer quaisquer outros tipos de respostas que sejam diferentes dos mencionados acima.
18. Selecione Mapear formato para modelo.
    * Esse mapeamento de modelo contém a definição do fluxo de dados para armazenar detalhes do documento de entrada analisado com o uso dos itens do modelo de dados.
19. Selecione Designer.
20. Na árvore, expanda 'format'.
21. Na árvore, expanda “formato\Respostas: Caso(Responses)'.
    * Examine a estrutura da fonte de dados de "formato". Os três tipos de resposta são oferecidos separadamente.
22. Na árvore, selecione “formato\Respostas: Caso(Responses)\aType'.
    * O item da fonte de dados "aType" foi adicionado para indicar o tipo de resposta e está associado ao item do modelo de dados "Tipo".
23. Selecione a guia Validações.
24. Na árvore, selecione 'Tipo = format.Responses.aType'.
    * A validação de ER foi configurada para informar ao usuário sobre a situação quando a estrutura de resposta não corresponde à confirmação sobre o envio da transação ou às informações sobre a última transação enviada (caso de resposta sem suporte).
25. Feche a página.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Executar mapeamento de modelo de formato de ER configurado para analisar arquivos de entrada

Você executará o mapeamento de modelo criado para fins de teste para ver como o formato de ER configurado analisará respostas de serviços de entrada. Esta etapa usa diferentes arquivos XML para simular diferentes tipos de respostas de serviços Web.

1. Abra o arquivo Response1.xml em um leitor xml, como um navegador da Web. Esse arquivo contém detalhes de confirmação sobre a transação concluída ("TraC" é o elemento raiz).
2. Selecione Executar.
    * Selecione Procurar e selecione o arquivo Response1.xml.
3. Selecione OK.
    * Revise a saída gerada. O tipo de resposta foi corretamente reconhecido e analisado (`ERModelEnumDataSourceHandler#EFSTA model#enumType#C` representa o caso de conclusão da transação).
    * Abra o arquivo Response2.xml em um leitor XML. Esse arquivo contém informações sobre a última transação enviada (`Tra` é o elemento raiz).
4. Selecione Executar.
    * Selecione Procurar e selecione o arquivo Response2.xml.
5. Selecione OK.
    * Revise a saída gerada. O tipo de resposta foi corretamente reconhecido e analisado (`ERModelEnumDataSourceHandler#EFSTA model#enumType#R` representa o caso de reinicialização do sistema).
    * Abra o arquivo Response3.xml em um leitor XML. Esse arquivo inicia no item raiz TraZ e essa estrutura não é configurada usando o formato de ER.
6. Selecione Executar.
    * Selecione Procurar e selecione o arquivo Response3.xml.
7. Selecione OK.
    * Revise a saída gerada. O tipo de resposta foi corretamente reconhecido como incompatível (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). A mensagem correspondente foi colocada no Log de Informações (de acordo com a configuração de validação de ER) e a maior parte do modelo de dados não foi preenchida.
    * Abra o arquivo Response4.xml em um leitor XML. A estrutura desse arquivo é praticamente igual à do arquivo analisado com êxito Response1.xml, exceto a sequência de elementos aninhados do elemento raiz "TraC".
8. Selecione Executar.
    * Selecione Procurar e selecione o arquivo Response4.xml.
9. Selecione OK.
    * Revise a saída gerada. O tipo de resposta foi corretamente reconhecido como incompatível (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). A mensagem correspondente foi colocada no Log de Informações e a maior parte do modelo de dados não foi preenchida. Esse comportamento é devido à configuração atual desse formato de ER pressupõe uma determinada sequência de elementos aninhados do item raiz do arquivo de entrada.
10. Feche a página.
11. Na árvore, selecione 'Respostas\Conclusão de transação\TraC'.
12. No campo Ordem de análise de elementos aninhados, selecione 'Qualquer'.
    * Selecione Qualquer no campo "Ordem de análise de elementos aninhados" para permitir qualquer sequência de elementos aninhados para este item XML raiz.
13. Selecione Salvar.
14. Selecione Mapear formato para modelo.
15. Selecione Executar.
    * Selecione Procurar e selecione o arquivo Response4.xml.
16. Selecione OK.
    * Revise a saída gerada. O tipo de resposta agora foi corretamente reconhecido como igual para o arquivo Response1.xml.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]