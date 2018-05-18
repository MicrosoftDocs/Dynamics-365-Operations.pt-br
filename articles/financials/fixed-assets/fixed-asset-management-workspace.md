---
title: "Espaço de trabalho de gerenciamento de ativos fixos"
description: "Este tópico fornece informações sobre o Espaço de trabalho de gerenciamento de ativos fixos Este espaço de trabalho mostra informações relacionadas a ativos fixos inseridos no sistema. Inclui uma exibição resumida e uma exibição de análise."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 8425387d4004e02e9b8adf9ba3b31a0b4e02b6e9
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---

# <a name="fixed-asset-management-workspace"></a>Espaço de trabalho de gerenciamento de ativos fixos

[!include [banner](../includes/banner.md)]

O espaço de trabalho de **Gerenciamento de ativos fixos** mostra informações relacionadas a ativos fixos inseridos no sistema. Este espaço de trabalho inclui uma exibição resumida e uma exibição de análise. A guia **Meu trabalho** mostra os blocos de resumo, detalhes de ativos fixos e informações relacionadas sobre os ativos fixos na empresa atual. Você também pode adicionar análise à seção de análise do Power BI diretamente no espaço de trabalho. A guia **Análise – todas as empresas** usa recursos do Microsoft Power BI para mostrar os visuais relacionados a ativos fixos em todas as empresas.

## <a name="my-work"></a>Meu trabalho

### <a name="summary"></a>Resumo

Os blocos na seção **Resumo** fornecem uma visão geral dos seus ativos fixos. As informações incluem métricas sobre os ativos que não foram adquiridos ainda, os que foram adquiridos durante o ano atual, e os que foram alienados durante o ano atual. A seção **Resumo** também possui navegação rápida para a página de lista de **Ativo fixo**, a proposta de depreciação de lote e o diário de ativo fixo.

### <a name="find-fixed-assets"></a>Localizar ativos fixos

A seção **Localizar ativos fixos** permite que você localize ativos rapidamente fornecendo o número do ativo fixo, o grupo, o nome, a localização ou a pessoa responsável. Todos os ativos que correspondem aos critérios de pesquisa aparecerão na lista.

Na lista, você pode visualizar as seguintes páginas:

 - Página de **Detalhes** do ativo fixo
 - Página de **Registros** referente a todos os registros associados ao ativo fixo
 - Página **Avaliações de ativos fixos**

### <a name="valuations"></a>Avaliações

A página **Avaliações de ativos fixos** permite visualizar, em uma página, as informações mais importantes sobre um ativo fixo, além de detalhes de todos os registros associados ao ativo fixo. A opção **Saldos** no canto superior esquerdo da página mostra a avaliação atual de cada registro associado ao ativo fixo. Você pode reverter os valores para conferir as transações detalhadas que compõem o valor de resumo. A opção **Perfil** no canto superior esquerdo da página mostra a agenda de depreciação de cada registro associado ao ativo fixo.

Você pode acessar a página **Avaliações de ativos fixos** do espaço de trabalho **Gerenciamento de ativos fixos** ou a página de lista de **Ativo fixo**.

### <a name="related-information"></a>Informações Relacionadas

É possível navegar diretamente para a página de **Configuração de registros**, página **Consulta de transações de ativo fixo**, bem como vários relatórios usando links na seção **Informações relacionadas** do espaço de trabalho.

### <a name="analytics--all-companies"></a>Análise – todas as empresas

A página de **Análise** fornece métricas importantes sobre os ativos fixos de todas as entidades legais do sistema. O acesso a esta guia é controlado pela análise de Exibir ativo fixo para todos os privilégios de segurança da empresa.

A tabela a seguir mostra as visualizações disponíveis em cada página de relatório.

| Página de relatório            | Visualização        |
|------------------------|----------------------|
| Avaliações de ativos fixos | Valor líquido contábil total |
| Avaliações de ativos fixos | Valores líquidos contábeis por grupo de ativo fixo |
| Avaliações de ativos fixos | Valores de aquisição |
| Avaliações de ativos fixos | Valores de alienação |
| Avaliações de ativos fixos | Detalhes do Ativo Fixo |
| Mapas de Avaliações        | Valor líquido contábil total |
| Mapas de Avaliações        | Localizações de ativos fixos |
| Mapas de Avaliações        | Detalhes do Ativo Fixo |

Para exibir a análise com os dados, primeiro você deve atualizar a medida agregada AssetTransactionMeasure na página **Repositório de Entidades**.

