---
title: "Gerenciar o ciclo de vida da configuração de relatório eletrônico"
description: "Este tópico descreve como gerenciar o ciclo de vida de configurações de Relatórios eletrônicos (ER) para a solução do Microsoft Dynamics 365 for Operations."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: cecbb5bd57aa24a942d10241bd83e4c1996a3805
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Gerenciar o ciclo de vida da configuração de relatório eletrônico

[!include[banner](../includes/banner.md)]


Este tópico descreve como gerenciar o ciclo de vida de configurações de Relatórios eletrônicos (ER) para a solução do Microsoft Dynamics 365 for Operations.

<a name="overview"></a>Visão Geral
--------

O relatório eletrônico (ER) é um mecanismo que oferece suporte a documentos eletrônicos específicos do país e exigidos pela regulamentação no Microsoft Dynamics 365 for Operations. Geralmente, o ER considera uma capacidade de executar as seguintes tarefas para um único documento eletrônico. Para obter mais detalhes, consulte [Visão geral do relatório eletrônico](general-electronic-reporting.md).

-   Projete um modelo para um documento eletrônico:
    -   Identifique as fontes de dados necessárias que podem ser apresentadas no documento:
        -   Os dados subjacentes do Dynamics 365 for Operations, como tabelas de dados, entidades de dados e classes.
        -   Propriedades específicas do processo, como data e hora da execução e fuso horário.
        -   Parâmetros de entrada do usuário, especificados pelo usuário final em tempo de execução.
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
    -   Defina configurações do Dynamics 365 for Operations de forma que comece a usar uma configuração de ER ao fazer referencia a essa configuração em um parâmetro relacionado ao processo Por exemplo, mencione a configuração de ER em um método Pagamento de contas a pagar específico para gerar uma mensagem de pagamento eletrônico para o processamento de faturas.
-   Use um modelo em um processo de negócios específico:
    -   Executar uma configuração de ER em um processo comercial específico. Por exemplo, para gerar uma mensagem de pagamento eletrônico para o processamento de faturas quando um método de pagamento que faz referência à configuração de ER é selecionado.

## <a name="concepts"></a>Conceitos
As funções e as atividades relacionadas a seguir estão associadas ao ciclo de vida de configuração de ER.

| Função                                       | Atividades                                                      | descrição                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consultor funcional de relatório eletrônico | Crie e gerencie componentes de ER (modelos e formatos).           | Um executivo, que projeta modelos de dados específicos de domínio de ER, cria os modelos necessários para documentos eletrônicos e os associa adequadamente.                                                                           |
| Desenvolvedor de relatório eletrônico             | Crie e gerencie mapeamentos de modelo de dados.                          | Um especialista do Dynamics 365 for Operations que seleciona as fontes de dados necessárias ao Dynamics 365 for Operations e as associa aos modelos de dados específicos do domínio de ER.                                                                 |
| Supervisor de contabilidade                      | Defina as configurações relacionadas ao processo que fazem referência a artefatos de ER. | Por exemplo, uma função **Supervisor de contabilidade** que permite que as configurações de uma configuração de ER sejam usadas em um método de pagamento específico de Contas a pagar para gerar uma mensagem do pagamento eletrônico para processar faturas. |
| Auxiliar de pagamentos de contas a pagar            | Use artefatos de ER em um processo de negócios específico.                | Por exemplo, uma função **Auxiliar de pagamentos de contas a pagar** que permite que as mensagens do pagamento eletrônico sejam geradas para processar faturas com base no formato de ER configurado para um método de pagamento específico.           |

## <a name="er-configuration-development-lifecycle"></a>Ciclo de vida de desenvolvimento de configuração de ER
Pelos seguintes motivos relacionados a ER, é recomendável projetar configurações de ER no ambiente de desenvolvimento como uma instância separada do Dynamics 365 for Operations:

-   Os usuários nas funções **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico** podem editar configurações e executá-las para fins de teste. Este cenário pode ocasionar chamadas de métodos de classes e de tabelas que podem prejudicar os dados de negócios e o desempenho do uso da instância do Dynamics 365 for Operations.
-   As chamadas de métodos de classes e de tabelas como fontes de dados de ER das configurações do ER não serão restringidas por pontos de entrada do Dynamics 365 for Operations e pelo conteúdo registrado da empresa. Portanto, os dados de negócios confidenciais podem ser acessados pelos usuários que desempenham a função **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico**.

As configurações de ER projetadas no ambiente de desenvolvimento podem ser carregadas no ambiente de teste da avaliação da configuração (integração adequada do processo, exatidão dos resultados e desempenho) e do controle de qualidade, como exatidão dos direitos de acesso orientados a funções e segregação de direitos. Os recursos que permitem a troca de configuração de ER podem ser usados com essa finalidade. Por fim, as configurações de ER comprovadas podem ser carregadas no LCS, onde poderão ser compartilhadas com os assinantes de serviço ou no ambiente de produção para uso interno, conforme mostrado na ilustração a seguir. ![Ciclo de vida da configuração do ER](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Consulte também
--------

[Visão geral do relatório eletrônico](general-electronic-reporting.md)




