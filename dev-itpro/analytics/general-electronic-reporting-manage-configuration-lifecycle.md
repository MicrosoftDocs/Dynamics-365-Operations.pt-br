---
title: "Gerenciar o ciclo de vida da configuração de relatório eletrônico"
description: "Este tópico descreve como gerenciar o ciclo de vida de configurações relatando eletrônicas de (ER) do Microsoft Dynamics 365 para a solução de operações."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: f4d8994f6548119789715a4879b6bc02d25598e9
ms.lasthandoff: 03/31/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Gerenciar o ciclo de vida da configuração de relatório eletrônico

Este tópico descreve como gerenciar o ciclo de vida de configurações relatando eletrônicas de (ER) do Microsoft Dynamics 365 para a solução de operações.

<a name="overview"></a>Visão Geral
--------

O relatório eletrônico (ER) é um mecanismo que oferece suporte a documentos eletrônicos específicos do país e exigidos pela regulamentação no Microsoft Dynamics 365 for Operations. Geralmente, o ER considera uma capacidade de executar as seguintes tarefas para um único documento eletrônico. Para obter mais detalhes, consulte visão geral eletrônica [] de relatório (general-electronic-reporting.md).

-   Projete um modelo para um documento eletrônico:
    -   Identifique as fontes de dados necessárias que podem ser apresentadas no documento:
        -   Dynamics subjacente dados 365 para operações, como tabelas de dados, dados de entidades, e classes.
        -   propriedades processo específicas, como a data de execução e hora, e fuso horário.
        -   Parâmetros de entrada do usuário, especificadas pelo usuário final em tempo de execução.
    -   Defina os elementos do documento necessários e a topologia deles para especificar o formato de um documento final.
    -   Configure o fluxo de dados desejado das fontes de dados selecionadas para elementos do documento definido via associações da fonte de dados aos componentes de formato do documento e especifique a lógica de controle de processos.
-   Crie um modelo disponível de forma que ele possa ser usado em outras instâncias do Dynamics 365 for Operations:
    -   Transforme um modelo de documento criado no Dynamics 365 for Operations em uma configuração de ER e exporte a configuração da instância atual do Dynamics 365 for Operations como um pacote XML que possa ser armazenado localmente ou em LCS.
    -   Transforme uma configuração de ER em um modelo de documento do Dynamics 365 for Operations.
    -   Importe um pacote XML armazenado localmente ou em LCS para a instância atual do Dynamics 365 for Operations.
-   Personalize o modelo de um documento eletrônico:
    -   Traga um modelo de LCS para a instância atual do Dynamics 365 for Operations como uma configuração de ER.
    -   Crie uma versão personalizada de uma configuração do ER e mantenha uma referência à versão base.
-   Integre um modelo a um processo comercial específico, para que ele fique disponível no Dynamics 365 for Operations:
    -   Defina configurações do Dynamics 365 for Operations de forma que comece a usar uma configuração de ER ao fazer referencia a essa configuração em um parâmetro relacionado ao processo Por exemplo, consulte o ER em um método de pagamento específico de contas a pagar para gerar uma mensagem de pagamento eletrônico para processar notas fiscais.
-   Use um modelo em um processo de negócios específico:
    -   Executar uma configuração de ER em um processo comercial específico. Por exemplo, para gerar uma mensagem de pagamento eletrônico para processar notas quando um método de pagamento que a configurações refere de ER é selecionado.

## <a name="concepts"></a>Conceitos
As seguintes funções e atividades relacionadas estão associadas ao ciclo de vida de configuração de ER.

| Função                                       | Atividades                                                      | descrição                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consultor funcional de relatório eletrônico | Crie e gerencie componentes de ER (modelos e formatos).           | Um executivo que criar modelos de domínio- dados específicos de ER, crie métodos necessários para documentos eletrônicos, os associe adequadamente.                                                                           |
| Desenvolvedor de relatório eletrônico             | Crie e gerencie mapeamentos de modelo de dados.                          | Uma para o dynamics 365 especialista de operações que necessário selecionar o dynamics 365 de fontes de dados e as operações associados a modelos de domínio- dados específicos de ER.                                                                 |
| Supervisor de contabilidade                      | Defina as configurações relacionadas ao processo que fazem referência a artefatos de ER. | Por exemplo, supervisor de contabilidade ** ** uma função que permite que as configurações da definição de ER são usadas em um método de pagamento específico de contas a pagar para gerar uma mensagem de pagamento eletrônico para processar notas fiscais. |
| Auxiliar de pagamentos de contas a pagar            | Use artefatos de ER em um processo de negócios específico.                | ** Por exemplo, os pagamentos de contas a pagar clerk ** uma função que permite que as mensagens de pagamento são geradas eletrônico processando faturas, com base no formato de ER configurado para um método de pagamento específico.           |

## <a name="er-configuration-development-lifecycle"></a>Ciclo de vida de desenvolvimento de configuração de ER
Pelos seguintes motivos relacionados a ER, é recomendável projetar configurações de ER no ambiente de desenvolvimento como uma instância separada do Dynamics 365 for Operations:

-   Os usuários nas funções **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico** podem editar configurações e executá-las para fins de teste. Este cenário pode ocasionar chamadas de métodos de classes e de tabelas que podem prejudicar os dados de negócios e o desempenho do uso da instância do Dynamics 365 for Operations.
-   As chamadas de métodos de classes e de tabelas como fontes de dados de ER das configurações do ER não serão restringidas por pontos de entrada do Dynamics 365 for Operations e pelo conteúdo registrado da empresa. Portanto, os dados de negócios confidenciais podem ser acessados pelos usuários que desempenham a função **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico**.

As configurações de ER criadas no ambiente de desenvolvimento podem ser cobradas ao ambiente de teste para a avaliação (integração configuração adequada de processo, exatidão de resultados, e desempenho) e o controle de qualidade, como a exatidão de direitos de acesso e segregação de deveres abstrato conduzidos. Recursos que permitem o intercâmbio de configuração de ER podem ser usados com essa finalidade. Finalmente, as configurações de provadas podem ser ER esses carregado para LCS, onde podem ser compartilhadas com assinantes de serviço, ou um ambiente de produção para uso interno, como mostrado na seguinte ilustração. ![Ciclo de configuração de ER](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Consulte também
--------

[Visão geral do relatório eletrônico](general-electronic-reporting.md)


