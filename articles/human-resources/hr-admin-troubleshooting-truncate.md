---
title: Evitar o truncamento de texto na hierarquia de posições e exportar para o Visio
description: Este artigo explica como resolver um problema em que os nomes de pessoas e cargos estão truncados quando os clientes exibem a hierarquia de cargos no Microsoft Dynamics 365 Human Resources. Texto truncado pode tornar difícil realizar um screenshot ou imprimir a hierarquia.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a03c8f340e8ebb2fb0440518c154ed3bdd0197f6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053242"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Evite texto truncado na hierarquia de posição e exporte para Visio

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Saída**

Quando um cliente exibe a hierarquia de cargos no Microsoft Dynamics 365 Human Resources, os nomes de pessoas e cargos estão truncados. Portanto, pode ser difícil realizar uma captura de tela, ou imprimir e distribuir a hierarquia.

![Hierarquia de posições](media/position-h.png)

**Causa**

Esse comportamento é por design.

**Resolução**

Infelizmente, os usuários não podem alterar facilmente o tamanho do texto. Entretanto, você pode exportar uma hierarquia de posição do Human Resources e depois importá-la para o Microsoft Visio. Embora o seguinte artigo tenha sido escrito para o Microsoft Dynamics AX 2012, o processo ainda se aplica ao Human Resources: [Exportar uma hierarquia de cargos para o Microsoft Visio](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Rastrear essas etapas para exportar para Visio.

1. No Human Resources, abra a página de lista **Posições**.

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

No Human Resources, você também pode usar o espaço de trabalho **Pessoas** para exibir algumas informações relativas à hierarquia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]