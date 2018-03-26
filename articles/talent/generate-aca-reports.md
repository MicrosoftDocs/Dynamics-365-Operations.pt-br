---
title: "Gerar relatórios segundo a Lei de Serviços de Saúde Acessíveis"
description: "Esta funcionalidade está disponível para auxiliar empregadores que precisam rastrear as informações relatadas nos formulários 1095-B e 1095-C, em apoio à parte do Mandato do Empregador da Lei de Serviços de Saúde Acessíveis. Observe que esta funcionalidade está habilitada somente para entidades legais nos Estados Unidos."
author: kherr75
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 1994edc5d6c932be3a285f9bb328a05504c90f07
ms.contentlocale: pt-br
ms.lasthandoff: 03/08/2018

---
# <a name="generate-affordable-care-act-reports"></a>Gerar relatórios segundo a Lei de Serviços de Saúde Acessíveis

[!include[banner](includes/banner.md)]

Esta funcionalidade está disponível para auxiliar empregadores que precisam rastrear as informações relatadas nos formulários 1095-B e 1095-C, em apoio à parte do **Mandato do Empregador** da Lei de Serviços de Saúde Acessíveis. Observe que esta funcionalidade está habilitada somente para entidades legais nos Estados Unidos.

## <a name="getting-started"></a>Introdução
Ao começar a rastrear informações de relatos nos formulários 1095-B e 1095-C, você deve, primeiramente, criar um ou mais grupos de cobertura de Serviços de Saúde Acessíveis. Esses grupos de cobertura de Serviços de Saúde Acessíveis serão usados para indicar a oferta de cobertura que foi fornecida a um funcionário, a participação do funcionário no prêmio mensal de menor custo (se o custo estiver acima da linha de pobreza estabelecida pelo governo), bem como o Safe Harbor usado pelo empregador, se aplicável. Usar grupos de cobertura de Serviços de Saúde Acessíveis permite que você gerencie as informações para esses campos sem precisar recorrer a cada registro de funcionário com as mesmas condições. Além disso, grupos de cobertura de Serviços de Saúde Acessíveis podem ser facilmente atribuídos a um ou mais funcionários utilizando, na página, a funcionalidade de atribuição em Massa.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Manter várias versões de um grupo de cobertura
Você pode manter várias versões de um grupo de cobertura, o que permite que você faça alterações que mantêm as informações do grupo atualizadas, sem ter que criar um novo grupo e reatribuir funcionários a ele quando há alterações na sua organização ou nos benefícios oferecidos. 

Após criar os grupos de cobertura de Serviços de Saúde Acessíveis que necessita, você pode escolher atribuir em massa os grupos aos funcionários usando a funcionalidade **Atribuição em massa**, ou você pode acessar cada funcionário e indicar se as informações da ACA (Lei de Serviços de Saúde) precisam ser rastreadas e reportadas a esse funcionário, bem como atribuir o funcionário a um grupo de cobertura de Serviços de Saúde Acessíveis.

Se as informações de cobertura de Serviços de Saúde Acessíveis não precisam ser rastreadas ou reportadas a um funcionário, por exemplo, se ele é um funcionário de meio período, o campo **Relatar cobertura** pode ser definido como Não. Embora cada funcionário para o qual a informação da ACA precisa ser rastreada tenha que ser atribuído a um grupo de cobertura de Serviços de Saúde Acessíveis, ainda é possível alterar as opções **Oferta de cobertura**, **Cota de custo do funcionário** e **Safe Harbor** em qualquer mês – ou meses – que precise de valores diferentes dos inseridos no grupo de cobertura de Serviços de Saúde Acessíveis.

Para inserir exceções a qualquer um dos valores do grupo de cobertura de Serviços de Saúde Acessíveis, clique no link da cobertura de Serviços de Saúde Acessíveis, encontrado na página de detalhes do Trabalhador, que se encontra na seção Informações adicionais, na guia Emprego.

## <a name="reporting-health-care-coverage"></a>Relatórios de cobertura do plano de saúde
Além de rastrear se uma cobertura de plano de saúde é oferecida a um funcionário de tempo integral, se o empregador oferece cobertura de saúde auto-segurada e patrocinada pelo empregador, estando o funcionário matriculado (independentemente de seu status de emprego ser de tempo integral ou meio período), informações adicionais precisam ser informadas no 1095-C. Cada empregado (incluindo dependentes) coberto pelos planos de benefícios patrocinados pelo empregador deve ser incluído no relatório pelos meses em que esteve coberto. 

Você pode indicar se o Plano de benefício deve ou não ser informado selecionando a caixa de seleção **Pode ser relatado segundo a ACA**.

Além disso, se os funcionários optarem por ter qualquer um de seus dependentes cobertos por um benefício, você pode indicar as datas em que o dependente foi coberto, referente a cada funcionário, na página Manter benefícios. Para indicar que o dependente está coberto pelo benefício, escolha o botão Editar no painel de ações da Guia Rápida Dependentes.

Na página **Gerenciador de data de cobertura de dependentes**, você pode indicar as datas em que o dependente foi coberto pelo benefício. Inserir datas nessa página selecionará automaticamente a caixa de seleção **Coberto** na página **Manter benefícios**.

## <a name="generate-1095b-and-1095c-forms"></a>Gerar formulários 1095B e 1095C
Você pode também gerar formulários 109-B e 1095-C do produto, e distribuí-los a cada um de seus funcionários. Gerando eletronicamente o 1095-C e os arquivos de transmissão 1094-C correspondentes, os quais podem ser usados para envio à IRS, eles também podem ser gerados a partir do sistema.  

Ao gerar o formulário 1095-C, insira o calendário ou ano fiscal adequado, bem como se desejar imprimir o formulário de três páginas ou o de duas páginas. O formulário de três páginas só é necessário se o Empregador forneceu cobertura auto-segurada e o funcionário tem mais de seis dependentes cobertos, incluindo ele mesmo. Ao gerar o formulário de duas páginas, o sistema detectará automaticamente se o funcionário tem mais de 6 dependentes cobertos e não incluirá esse funcionário ao gerar o formulário. Além disso, ao gerar o formulário de três páginas, o sistema incluirá somente os funcionários que têm mais de seis dependentes cobertos.

## <a name="viewing-information"></a>Visualizando informações
Você pode usar a página **Cobertura de Serviços de Saúde Acessíveis do Trabalhador** para visualizar os funcionários que foram atribuídos a cada grupo de cobertura, os funcionários que não precisam ser incluídos em um relatório, e os funcionários que não foram atribuídos.

Se algum dos valores padrão do grupo de cobertura de Serviços de Saúde Acessíveis tiver sido substituído, um asterisco aparecerá ao lado do valor que foi alterado. Se os valores para todos os 12 meses forem iguais e não tiverem sido substituídos, o valor será impresso na coluna **Todos os 12 meses**.

Você também pode usar a janela de consulta para entender quais funcionários foram marcados por não poderem ser relatados segundo a ACA, o que significa que você não precisa rastrear se a cobertura foi oferecida a eles e não precisará emitir um 1095-C no final do ano. Ao selecionar **Não pode ser relatado segundo a ACA** no campo **Filtrar por**, você pode gerar uma lista de todos os funcionários que foram sinalizados para não receber um 1095-C.

Além de exibir uma lista de funcionários que não podem ser relatados segundo a ACA, você também pode exibir todos os funcionários que não foram atribuídos (o campo **Cobertura de relatório da ACA** está vazio) ou que foram atribuídos a um grupo de cobertura de Serviços de Saúde Acessíveis que expirou no ano selecionado no campo **Ano**.

Você pode exportar listas de funcionários que foram geradas usando qualquer uma das opções de filtragem para o Excel.

Caso seja necessário relatar pessoas cobertas porque, como empregador, você fornece cobertura auto-segurada, você também pode exibir todos os dependentes cobertos por planos de benefícios que foram marcadas como **Pode ser relatado segundo a ACA**, selecionando a ação de cobertura Exibir Dependente na faixa do painel de ação.

**Observação:** Somente benefícios cujo plano foi marcado como **Pode ser relatado segundo a ACA** serão exibidos na janela de consulta.

