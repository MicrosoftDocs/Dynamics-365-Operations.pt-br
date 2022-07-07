---
title: Configurar sequências numéricas para demonstrativos de varejo
description: Este artigo descreve como configurar as sequências numéricas necessárias para demonstrativos de varejo no Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 917d7b7a905a822ca3b1e074055fe0cd4af5555b
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027177"
---
# <a name="set-up-number-sequences-for-retail-statements"></a>Configurar sequências numéricas para demonstrativos de varejo

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar as sequências numéricas necessárias para demonstrativos de varejo no Microsoft Dynamics 365 Commerce.

No Dynamics 365 Commerce, dois tipos de demonstrativos de varejo são usados: 

- Os **demonstrativos transacionais** devem ser criados e lançados em uma frequência alta. São usados para lançar todas as transações não financeiras na loja para o Dynamics 365 Commerce headquarters. 
- Os **demonstrativos financeiros** devem ser criados e lançados uma vez por dia útil. Eles incluem somente turnos fechados das lojas de varejo que foram carregados para o Commerce headquarters por meio do trabalho p.

## <a name="configure-a-number-sequence-for-statement-posting"></a>Configurar uma sequência numérica para lançamento de demonstrativo

Depois de concluir a configuração de uma loja de varejo, no Commerce headquarters, você deve configurar uma sequência numérica exclusiva que será usada para demonstrativos durante o processo de criação de demonstrativos.

Para configurar uma sequência numérica para o lançamento de demonstrativo no Commerce headquarters, siga estas etapas:

1. Acesse **Administração da organização \> Sequências numéricas \> Sequências numéricas**.
1. Selecione **Novo \> Sequência numérica** para criar um novo registro.
1. Na Guia Rápida **Identificação**, no campo **Código de sequência numérica**, insira o código de sequência numérica.
1. No campo **Número de sequência do nome**, insira um nome.
1. Na Guia Rápida **Parâmetros do escopo**, no campo **Escopo**, selecione **Unidade operacional**.
1. No campo **Unidade operacional**, selecione a loja para a qual a sequência numérica será usada.
1. Na guia rápida **Segmentos**, defina os segmentos.
1. Na guia rápida **Referências**, defina o campo **Área** como **Loja de varejo**.
1. Defina o campo **Referência** como **Número do demonstrativo** e, em seguida, selecione **OK**.

    ![Guias rápidas de identificação, parâmetros de escopo, segmentos e referências na página Sequências numéricas.](media/retail-statements-num-seq-setup-01.png)

1. Na guia rápida **Geral**, na seção **Alocação de números**, atualize os campos **Menor** e **Maior** para que correspondam ao tamanho do **Segmento alfanumérico** definido na guia rápida **Segmentos**.
1. Na guia rápida **Desempenho**, recomendamos que você defina a opção de **Pré-alocação** como **Sim** e o campo **Quantidade de números** como **25**.

    ![Guias rápidas Geral e Desempenho na página Sequências numéricas.](media/retail-statements-num-seq-setup-02.png)

1. No Painel de Ação, selecione **Salvar** para salvar suas mudanças e fechar a página.
