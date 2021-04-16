---
title: Emitir faturas eletrônicas no Finance e no Supply Chain Management
description: Este tópico explica como emitir faturas eletrônicas no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management por meio do Faturamento eletrônico.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8d6ef59b64a96e13bdc2e5ddf299ef7ab98e105c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840067"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Emitir faturas eletrônicas no Finance e Supply Chain Management

[!include [banner](../includes/banner.md)]

Este tópico explica como emitir faturas eletrônicas no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management por meio do Faturamento eletrônico.


## <a name="feature-activation"></a>Ativação de recurso

Para emitir faturas eletrônicas por meio do Faturamento eletrônico, você deverá ativar a referência do recurso no Finance e no Supply Chain Management.

Cada recurso corresponde a um recurso de faturamento eletrônico específico que atende aos requisitos de faturamento eletrônico para um país/região.

A tabela a seguir mostra a lista de recursos que podem ter suporte do Faturamento eletrônico.

| Organização                                              | País/região |
|---------------------------------------------------|----------------|
|Fatura eletrônica austríaca                        |Áustria         |
|Fatura eletrônica belga                         |Bélgica         |
|NF-e Federal - Fatura eletrônica brasileira       |Brasil          |
|NFS-e: fatura eletrônica de serviços brasileira (municipal)|Brasil          |
|Fatura eletrônica dinamarquesa                          |Dinamarca         |
|Fatura eletrônica egípcia                        |Egito           |
|Fatura eletrônica estoniana                        |Estônia         |
|Fatura eletrônica finlandesa                         |Finlândia         |
|Fatura eletrônica francesa                          |França          |
|Fatura eletrônica alemã                          |Alemanha         |
|PEPPOL: fatura eletrônica global                 |Global          |
|Fatura eletrônica italiana                         |Itália           |
|CFDI: fatura eletrônica mexicana                  |México          |
|Fatura eletrônica holandesa                           |Países Baixos     |
|Fatura eletrônica norueguesa                       |Noruega          |
|Fatura eletrônica espanhola                         |Espanha           |

Quando houver um recurso Faturamento eletrônico herdado com suporte no escopo de localizações do país/região, a ativação desses recursos desativa o recurso herdado e habilita a emissão das faturas eletrônicas por meio do Faturamento eletrônico.

> [!IMPORTANT]
> Depois que o recurso integração do Faturamento eletrônico for habilitado, a nova experiência de Faturamento eletrônico será desativada por padrão. Você pode usar o conceito de recurso para habilitar seletivamente novas experiências para entidades legais usando funcionalidades específicas de país/região. A opção **Global** controla a nova experiência para os países/regiões restantes que não estão listados especificamente na tabela.

## <a name="submit-electronic-documents"></a>Enviar documentos eletrônicos

O processo de envio de documentos eletrônicos representa o único ponto de comunicação entre o Finance e o Supply Chain Management e o Faturamento eletrônico. Durante cada evento de envio, os fluxos de comunicação nas duas direções:

- **Do Finance e Supply Chain Management para o Faturamento eletrônico** – o Finance e o Supply Chain Management enviam as faturas abstratas para o Faturamento eletrônico. Conforme necessário, eles também enviam o conteúdo de variáveis que foram configuradas como parte dos recursos de faturamento eletrônico.
- **Do Faturamento eletrônico para o Finance e o Supply Chain Management** – dependendo do recurso de faturamento eletrônico, o Finance e o Supply Chain Management recebem atualizações do Faturamento eletrônico sobre os resultados de processamento de faturas que foram previamente enviadas. Eles também recebem o conteúdo de variáveis que foram configuradas como parte dos recursos de faturamento eletrônico.

Para enviar documentos eletrônicos para o Faturamento eletrônico, no Finance e no Supply Chain Management, acesse **Administração da organização &gt; Periódico &gt; Documentos eletrônicos &gt; Enviar documentos eletrônicos**.

O ponto de partida é uma fatura lançada. Essa fatura pode ter origens diferentes, como ordens de venda, faturas de projeto ou faturas de texto livre.

O processo de envio pode ser executado manualmente ou em segundo plano.

- **Execução manual** – para execução manual, você deve usar a opção **Filtro** para definir o intervalo de documentos que devem ser enviados. Na página **Filtros**, você pode configurar sua própria consulta para selecionar as faturas lançadas que devem ser enviadas. Após a seleção, você deve iniciar manualmente a execução do processamento e esperar que ela seja concluída. Quando o processamento é concluído, uma mensagem na Central de ações mostra o número de documentos eletrônicos que foram enviados com êxito.
- **Execução em segundo plano** – a execução em segundo plano é executada sem exigir que você se conecte ou mantenha a caixa de diálogo de envio aberta. Você pode programar o processo para ser executado e definir a frequência de execução.

## <a name="view-the-submission-logs"></a>Exibir os logs de envio

No Finance e no Supply Chain Management, você pode usar os logs de envio para exibir os resultados do processamento do envio para o Faturamento eletrônico. Acesse **Administração da organização &gt; Periódico &gt; Documentos eletrônicos &gt; Envio de documentos eletrônicos**. Depois, no campo **Tipo de documento**, selecione um valor para filtrar o tipo de faturas que os logs mostram.

Há três status de envio possíveis:

- **Agendado** – o Faturamento eletrônico recebeu o envio do Finance e do Supply Chain Management, e o processamento do recurso de faturamento eletrônico está em andamento.
- **Concluído** – o Faturamento eletrônico processou com êxito o recurso de faturamento eletrônico, pois estava configurado para executá-lo.
- **Falha** – o Faturamento eletrônico encontrou um erro ou foi interrompido por uma exceção durante o processamento do recurso de faturamento eletrônico.

> [!IMPORTANT]
> O status do envio se refere ao status do processamento que o Faturamento eletrônico faz no recurso de faturamento eletrônico. Ele não se refere ao status final da própria fatura eletrônica.
>
> Por exemplo, se uma fatura eletrônica precisar ser enviada para um serviço Web externo para aprovação, o status de envio poderá ser **Concluído**, mas o status da fatura eletrônica poderá ser **Rejeitado**. Nesse caso, o Faturamento eletrônico conseguiu processar com êxito o recurso de faturamento eletrônico, pois estava configurado para processar esse recurso. No entanto, a fatura eletrônica foi rejeitada porque não atendeu aos critérios estabelecidos pelo serviço Web para a aprovação da fatura.

Os logs de envio incluem as seguintes funções adicionais:

- **Detalhes do envio** – exiba os detalhes do envio principal. A visualização mostra o log de execução completo das ações que são configuradas no recurso de faturamento eletrônico. Ela também permite que os usuários baixem os arquivos criados durante o processamento. Em cenários em que a fatura deve ser aprovada por um serviço Web externo, ela permite que os usuários exibam o status da fatura.
- **Envios relacionados** – exiba os detalhes de envios secundários.
- **Cancelar envios** – esta função habilita um processo de envio especial em cenários nos quais a fatura eletrônica deve ser aprovada por um serviço Web externo. Ela instrui o Faturamento eletrônico a enviar ao serviço Web uma mensagem específica que pretende cancelar o status de uma fatura eletrônica aprovada no banco de dados do serviço Web.
- **Reenviar documento** – reenvie um documento eletrônico que já foi enviado ao Faturamento eletrônico. Um log novo é criado na página **Detalhes do envio**.
- **Enviar envio relacionado**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
