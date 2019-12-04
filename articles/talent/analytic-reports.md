---
title: Usar relatórios analíticos no Attract
description: Este tópico descreve os relatórios analíticos para insights do processo de contratação no Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 4ae608bbca111313d8c77e63f6a7a95813f6e5cd
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833222"
---
# <a name="use-analytic-reports-in-attract"></a>Usar relatórios analíticos no Attract

[!include [banner](includes/banner.md)]

Os relatórios analíticos no Microsoft Dynamics 365 Talent: Attract fornecem uma solução pronta para uso (OOTB) para insights do processo de contratação. Os recursos disponíveis incluem:

- **Análise de trabalho:** clique na guia **Análise** dentro de um trabalho para métricas sobre os candidatos do trabalho.
- **Hub de análise:** clique em **Análise** na navegação à esquerda, para métricas agregadas nas tarefas.
- **Segurança específica do usuário**: o acesso a relatórios é controlado pela [função](security-attract.md) do Attract e a função de participante do trabalho.
- **Filtragem cruzada:** clique nos elementos visuais em um relatório para visualizar outras métricas filtradas pelos dados selecionados.

>[!NOTE] 
>- Este recurso está atualmente em [visualização](access-preview-feature.md). Para experimentá-lo, você deve ter o [**Complemento de Contratação Abrangente**](attract-comprehensive-hiring.md).
>- Todos os relatórios públicos de visualização são exibidos em inglês.
>- Relatórios são atualizados a cada 3 horas. A hora da última atualização (no fuso horário local) está localizada na parte superior do relatório. As horas de atualização são uma aproximação e variam com base no volume de dados e na carga de recursos na sua região.

## <a name="job-analytics"></a>Análise de Trabalho

Os relatórios Análise de trabalho são um snapshot do processo de contratação de um trabalho.  Principais métricas incluem:

- Candidatos ativos por estágio
- Origem do candidato
- Tipo do candidato (interna ou externa)

## <a name="analytics-hub"></a>Hub de análise

Os relatórios Hub de análise agregam dados entre tarefas para destacar tendências no processo de contratação. O Attract inclui dois relatórios OOTB: Resumo de pipeline e Análise em forma de funil.

### <a name="pipeline-summary"></a>Resumo do Pipeline

O relatório Resumo de pipeline agrega dados para trabalhos abertos. Principais métricas incluem:

- Candidatos em todos os trabalhos por estágio
- Origem do candidato
- Posições abertas por nível de tempo de serviço

### <a name="funnel-analysis"></a>Análise em forma de funil

O relatório Análise em forma de funil agrega dados para trabalhos que foram fechados como preenchidos. Principais métricas incluem:

- Tempo para contratar
- Métricas de conversão (ao passar o mouse)
- Taxa de aceitação da oferta

Observação: no momento mais preciso para contratação de relatórios, é recomendável que você use [Gerenciamento de ofertas](offer-setup.md), um recurso disponível como parte do Complemento de Contratação Abrangente.

>[!TIP] 
>Tente passar o mouse sobre os recursos visuais para obter informações adicionais. Por exemplo, passar o mouse sobre os recursos visuais **Candidatos ativos** exibirá os dias médios no estágio. A análise dessas informações pode fornecer insights essenciais para reduzir o tempo de contratação e permitir que os recrutadores se concentrem em maneiras de reduzir o tempo gasto em cada estágio.

## <a name="user-specific-security"></a>Segurança específica do usuário

Os relatórios do Attract podem ser acessados para as [funções](security-attract.md) Administrador, Ler tudo, Recrutador e Gerente de contratação. Os usuários não atribuídos não têm acesso a nenhuma das páginas do relatório analítico (Análise de trabalho ou Hub de análise).

Os relatórios Análise de trabalho exibem dados para o trabalho selecionado. O Hub de análise reúne dados agregados em todos os trabalhos que um usuário pode visualizar. Os usuários que podem visualizar Meus trabalhos e Todos os trabalhos na página Trabalhos têm as mesmas visualizações disponíveis no Hub de análise.

## <a name="cross-filter"></a>Filtro cruzado

Um dos grandes recursos do Power BI é a forma como todos os recursos visuais de uma página de relatório são interconectados. Se você selecionar um ponto de dados em um dos recursos visuais, todos os outros recursos visuais na página que contêm esses dados serão alterados com base nessa seleção. Saiba mais e veja um exemplo em [Como os visuais realizam filtragem cruzada entre si em um relatório do Power BI](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).

## <a name="export-to-excel"></a>Exportar para o Excel

Para visualizar os dados do relatório no Excel, você pode clicar no menu de opções (três pontos) em um visual e selecionar **Exportar dados subjacentes**. Os dados exportados serão exportados como filtrados, respeitando as permissões do usuário no Attract. Para obter mais informações, consulte [Exportar dados de visualizações](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).
