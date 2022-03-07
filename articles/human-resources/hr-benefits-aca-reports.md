---
title: Gerar relatórios segundo o Affordable Care Act (ACA)
description: Relatórios de Affordable Care Act (ACA - Lei de Serviços de Saúde Acessíveis) gera formulários 1095-B e 1095-C para dar suporte à parte **obrigatória do empregador** do ACA.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c8f336e31e77391ef7e2bc2dca901e6a78fbb914
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066992"
---
# <a name="generate-aca-reports"></a>Gerar relatórios ACA


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Relatórios de Affordable Care Act (ACA - Lei de Serviços de Saúde Acessíveis) gera formulários 1095-B e 1095-C para dar suporte à parte **obrigatória do empregador** do ACA.

> [!NOTE]
> O relatório ACA só é habilitado para entidades legais nos Estados Unidos.

## <a name="getting-started"></a>Introdução

Para rastrear informações dos formulários 1095-B e 1095-C, primeiro crie um ou mais grupos de cobertura de Serviços de Saúde Acessíveis. Os grupos de cobertura de Serviços de Saúde Acessíveis indicam:

- A oferta de cobertura para um funcionário
- A cota do funcionário com o menor custo mensal se o custo estiver acima da linha de pobreza estabelecida pelo governo
- Safe Harbor usado pelo empregador, se aplicável

Grupos de cobertura de Serviços de Saúde Acessíveis permitem que você gerencie as informações desses campos sem alterar cada registro de funcionário com as mesmas condições. Você pode facilmente atribuir grupos de cobertura de Serviços de Saúde Acessíveis a um ou mais funcionários, utilizando a opção de **Atribuição em massa** na página.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Manter várias versões de um grupo de cobertura

Você pode manter várias versões de qualquer grupo de cobertura. Essa funcionalidade permite fazer alterações sem precisar criar um novo grupo e reatribuir funcionários a ele. 

Depois de criar grupos de cobertura de ACA, você pode atribuir os grupos em massa a funcionários com a opção **Atribuição em massa**. Você também pode indicar individualmente se deseja rastrear e relatar informações de ACA e atribuir um funcionário a um grupo de cobertura de Serviços de Saúde Acessíveis.

Não é necessário rastrear algumas informações de cobertura de ACA, por exemplo, para funcionários de meio expediente. Nesse caso, defina o campo **Cobertura do relatório** como **Não**. Embora seja necessário atribuir a cada funcionário com informações de ACA rastreáveis um grupo de cobertura de Serviços de Saúde Acessíveis, você ainda pode alterar as seguintes opções para meses com valores diferentes:

- **Oferta de cobertura**
- **Cota de custo do funcionário**
- **Safe Harbor**

Para inserir exceções para valores do grupo de cobertura de Serviços de Saúde Acessíveis, selecione o link de **Cobertura de Serviços de Saúde Acessíveis** na página **Detalhes do trabalhador** na seção **Informações adicionais** na guia **Emprego**.

## <a name="reporting-health-care-coverage"></a>Relatórios de cobertura do plano de saúde

Além de rastrear se uma cobertura de plano de saúde oferecida a funcionários de tempo integral, se o empregador oferecer cobertura de saúde auto-segurada e patrocinada pelo empregador, na qual o funcionário esteja matriculado (independentemente do status de emprego ser tempo integral ou meio expediente), informações adicionais precisam ser relatadas no 1095-C. Cada empregado (incluindo dependentes) coberto pelos planos de benefícios patrocinados pelo empregador deve ser incluído no relatório pelos meses em que esteve coberto. 

Você pode indicar se o plano de benefícios deve ou não ser relatado marcando a caixa de seleção **Pode ser relatado segundo a ACA**.

Além disso, se os funcionários optarem por ter qualquer um dos dependentes cobertos por um benefício, você poderá indicar as datas em que o dependente foi coberto, referente a cada funcionário, na página **Manter benefícios**. Para indicar que o dependente está coberto pelo benefício, selecione o botão **Editar** no painel de ações da FastTab **Dependentes**.

Na página **Gerenciador de data de cobertura de dependentes**, você pode indicar as datas em que o dependente foi coberto pelo benefício. Inserir datas nessa página selecionará automaticamente a caixa de seleção **Coberto** na página **Manter benefícios**.

## <a name="generate-1095-b-and-1095-c-forms"></a>Gerar formulários 1095-B e 1095-C

Você pode também gerar formulários 1095-B e 1095-C no produto e distribuí-los a cada um dos funcionários. O sistema também pode gerar eletronicamente formulários 1095-C e os arquivos de transmissão IRS 1094-C.  

Ao gerar o formulário1095-C, insira o ano fiscal adequado e indique se os números de seguro social devem ser mascarados. Se você estiver imprimindo formulários 1095-C para mais de 500 funcionários, receberá mais de um arquivo PDF. É recomendável aumentar o **Tamanho máximo do arquivo** na janela **Parâmetros de gerenciamento de documentos** para 150 MB.

## <a name="viewing-information"></a>Visualizando informações

Você pode usar a página **Cobertura de Serviços de Saúde Acessíveis do Trabalhador** para visualizar os funcionários que foram atribuídos a cada grupo de cobertura, os funcionários que não precisam ser incluídos em um relatório, e os funcionários que não foram atribuídos.

Se algum dos valores padrão do grupo de cobertura de Serviços de Saúde Acessíveis tiver sido substituído, um asterisco aparecerá ao lado do valor que foi alterado. Se os valores para todos os 12 meses forem iguais e não tiverem sido substituídos, o valor será impresso na coluna **Todos os 12 meses**.

Você também pode usar a janela de consulta para saber quais funcionários foram sinalizados como Não pode ser relatado segundo a ACA. Não é necessário rastrear se a cobertura foi oferecida a eles e nem emitir um 1095-C no final do ano. Selecione **Não pode ser relatado segundo a ACA** no campo **Filtrar por** para gerar uma lista de todos os funcionários que não receberão um 1095-C.

Além disso, você pode exibir uma lista de funcionários que não foram atribuídos (o campo **Cobertura de relatório da ACA** está vazio) ou que foram atribuídos a um grupo de cobertura de Serviços de Saúde Acessíveis que expirou no ano selecionado no campo **Ano**.

Você pode exportar listas de funcionários que foram geradas usando qualquer uma das opções de filtragem para o Excel.

Se você precisar relatar as pessoas cobertas porque fornece cobertura auto-segurada, poderá exibir os dependentes cobertos por planos de benefícios marcados como **Pode ser relatado segundo a ACA**. Selecione **Exibir Cobertura de Dependentes** no painel de ações.

> [!NOTE]
> Somente planos de benefícios marcados como **Pode ser relatado segundo a ACA** são exibidos na janela de consulta.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
