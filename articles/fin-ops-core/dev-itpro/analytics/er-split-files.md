---
title: Dividir os arquivos XML gerados com base no tamanho do arquivo e na quantidade de conteúdo
description: Este artigo fornece informações sobre como dividir os arquivos gerados com base tamanho do arquivo e na quantidade de itens de conteúdo
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 5347d4e85198893dd94f14508176db93ccd47c22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280085"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Dividir os arquivos XML gerados com base no tamanho do arquivo e na quantidade de conteúdo

[!include[banner](../includes/banner.md)]

Você pode criar os formatos de relatórios eletrônicos (ER) para gerar documentos de saída no formato XML. Às vezes, esses documentos podem ser aceitos somente quando atendem a critérios específicos, como um tamanho máximo do arquivo ou número máximo de alguns nós de XML. Você pode criar formatos de ER para gerar documentos eletrônicos que satisfazem aos requisitos que os destinatários desses documentos especificam.

- Para o elemento de formato de arquivo, você poderá definir um limite de tamanho de arquivo como uma expressão de ER. Se o limite definido for excedido quando um relatório de ER for gerado, o ER termina a criação do arquivo atual e, em seguida, move-se para criar o próximo arquivo.
- Para qualquer formato de elemento XML, você pode definir um limite sobre o número de elementos como uma expressão de ER. Se o número de nós de XML no arquivo que foi gerado exceder o limite definido quando um relatório de ER for executado, o ER finaliza a criação do arquivo atual e move-se para criar o próximo arquivo.
- Para qualquer elemento de formato de sequência de XML, você pode definir um limite sobre o número de elementos filhos como uma expressão de ER. Se o número de nós de XML aninhados do elemento do formato no arquivo gerado exceder o limite definido quando um relatório de ER for executado, o ER finaliza a criação do arquivo atual e move-se para criar o próximo arquivo.
- Você pode marcar qualquer formato de elemento XML como sem interrupção. Assim, você pode manter itens aninhados dos XML gerados no elemento de formato em um único arquivo gerado.

Além de usar os elementos de formato do Elemento XML e da Sequência de XML para adicionar nós XML ao arquivo gerado, você pode usar o elemento de formato XML de RAW. Porém, os nós adicionados usando o elemento de formato XML bruto não são considerados quando o número de nós é calculado para avaliar os limites sobre o número de elementos.

Se você configurou destinos de arquivo para um elemento de formato de arquivo que foi configurado para dividir a saída gerada, sempre que os limites específicos forem excedidos, cada parte da saída gerada será enviada para o destino de arquivo configurado como um arquivo individual. Para nomear exclusivamente os arquivos que foram criados dividindo a saída, você deve configurar uma expressão de EX para o elemento de formato de arquivo. Se você incluir uma fonte de dados de ER de tipo da sequência de número, a sequência numérica será incrementada para cada parte da saída da divisão.

Para saber mais sobre esse recurso, execute os guias de tarefa **ER Dividir arquivos XML com base do tamanho do arquivo ou na quantidade do item de conteúdo**, que faz parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677)** e podem ser baixados do [Centro de Download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Este guia de tarefas o orienta pelo processo de configuração de um formato de ER para dividir os arquivos gerados com base nos limites de tamanho de arquivo e quantidade de itens de conteúdo. Para concluir o guia de tarefas, baixe os seguintes arquivos:

- [Configuração do modelo de ER - XmlFilesSplittingModel.xml](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [Configuração de formato de ER - XmlFilesSplittingFormat.xml](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a>Recursos adicionais
[Destinos de relatório eletrônico (ER)](electronic-reporting-destinations.md)

[Designer de fórmulas no relatório eletrônico (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
