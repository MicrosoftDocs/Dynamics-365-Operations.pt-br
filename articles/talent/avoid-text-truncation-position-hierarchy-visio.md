---
title: Evite texto truncado na hierarquia de posição e exporte para Visio
description: Este tópico explica como resolver um problema em que os nomes de pessoas e cargos estão truncados quando os clientes exibem a hierarquia de cargos no Microsoft Dynamics 365 for Talent. Texto truncado pode tornar difícil realizar um screenshot ou imprimir a hierarquia.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 87d1c1994b14fac45fa305a9223ed45ee363a70c
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "859888"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Evite texto truncado na hierarquia de posição e exporte para Visio

[!include [banner](includes/banner.md)]

**Saída**

Quando um cliente exibe a hierarquia de cargos no Microsoft Dynamics 365 for Talent, os nomes de pessoas e cargos estão truncados. Portanto, pode ser difícil realizar uma captura de tela, ou imprimir e distribuir a hierarquia.

![Hierarquia de posições](media/position-h.png)

**Causa**

Esse comportamento é por design.

**Resolução**

Infelizmente, os usuários não podem alterar facilmente o tamanho do texto. Entretanto, você pode exportar uma hierarquia de posição de fora do Talent e depois importá-lo no Microsoft Visio. Embora o artigo a seguir tenha sido escrito para o Microsoft Dynamics AX 2012, o processo ainda se aplica ao Talent: [Exportar uma hierarquia de cargos para o Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Rastrear essas etapas para exportar para Visio.

1. No Talent, abra a página de lista **Posições**.

    Para incluir mais informações no diagrama de estrutura organizacional, adicione os campos à lista **Posições**, de forma que esteja disponível quando você usar o assistente posteriormente neste procedimento.

2. No Painel de Ação, selecione o botão **Abrir no Microsoft Office** e, em **Exportar para o Excel**, selecione **Cargos**. Alternativamente, pressione Ctrl+T.

    ![Exporte a página de lista de Posições para Excel](media/org-admin.png)

3. Salve o arquivo Excel que é exportado.

    ![Exportar para a caixa de diálogo do Excel](media/export-excel.png)

4. Em Visio, selecione **Visio - Criar novo**, e selecione a categoria de modelo **Empresarial**.

    ![Diagrama novo](media/new.png)

5. Selecione **Assistente de gráfico organizacional**, e depois selecione **Criar**.

    ![Caixa de diálogo do assistente do diagrama organizacional](media/orgchart-wizard.png)

6. Selecione **Informações que já estão armazenadas em um arquivo ou banco de dados**, e depois selecione **Avançar**.

    ![Assistente de cronograma organizacional 1](media/orgchart-wizard7.png)

7. Escolha **A text, Org Plus (\*.txt), ou arquivo Excel**, e depois selecione **Avançar**.

    ![Assistente de cronograma organizacional 2](media/orgchart-wizard3.png)

8. Navegue para selecionar o arquivo Excel exportado que contém a hierarquia de posição, e depois selecione **Avançar**.

    ![Assistente de cronograma organizacional 3](media/orgchart-wizard2.png)

9. Defina o campo **Nome** como **Posição**, defina o campo **Relatar a** como **Relatar a posição**, e depois selecione **Avançar**.

    ![Assistente de cronograma organizacional 4](media/orgchart-wizard1.png)

10. Selecione os campos que precisam ser mostrados em cada nó, e depois selecione **Avançar**.

    ![Assistente de cronograma organizacional 5](media/orgchart-wizard5.png)

11. Adicione a coluna **Posição** para a lista **Campos de dados de forma**, e depois selecione, **Avançar**.

    ![Assistente de cronograma organizacional 6](media/orgchart-wizard6.png)

12. As imagens não estão disponíveis atualmente. Portanto, na página seguinte, selecione **Avançar**.
13. Selecione **Desejo que o assistente interrompa automaticamente meu gráfico de organização entre páginas**.

    ![Assistente de cronograma organizacional 7](media/orgchart-wizard4.png)

14. Selecione **Concluir**.

    Se houver qualquer posição que não seja a estrutura, você será solicitado a incluí-la no diagrama.

O diagrama gerado em Visio mostra cada gerente em uma planilha separada.

Com base nos campos que você selecionou para incluir no diagrama, cada nó mostra as informações apropriadas quando o arquivo Visio é gerado.

![Diagrama de hierarquia](media/hierarchy.png)

**Opção adicional**

Em Talent, você também pode usar o espaço de trabalho **Pessoas** para exibir algumas informações relacionadas de hierarquia.
