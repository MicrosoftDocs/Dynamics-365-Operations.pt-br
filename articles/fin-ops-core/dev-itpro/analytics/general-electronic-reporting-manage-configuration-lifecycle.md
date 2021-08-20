---
title: Gerenciar o ciclo de vida da configuração de relatório eletrônico (ER)
description: Este tópico descreve como gerenciar o ciclo de vida de configurações de Relatório Eletrônico (ER) para o Dynamics 365 Finance.
author: NickSelin
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8b61082cf17707c952b6e07613769a671c349bb8fa92c21e3fe8524ef62dcb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767770"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Gerenciar o ciclo de vida da configuração de Relatório eletrônico (ER)

[!include [banner](../includes/banner.md)]

Este tópico descreve como gerenciar o ciclo de vida de configurações de Relatório Eletrônico (ER) para o Dynamics 365 Finance.

## <a name="overview"></a>Visão Geral

O relatório eletrônico (ER) é um mecanismo que oferece suporte a documentos eletrônicos específicos do país/região e exigidos pela regulamentação. Geralmente, o ER considera uma capacidade de executar as seguintes tarefas para um único documento eletrônico. Para obter mais detalhes, consulte [Visão geral de ER (Relatórios eletrônicos)](general-electronic-reporting.md).

- Projete um modelo para um documento eletrônico:

    - Identifique as fontes de dados necessárias que podem ser apresentadas no documento:

        - Os dados subjacentes, como tabelas de dados, entidades de dados e classes.
        - Propriedades específicas do processo, como data e hora da execução e fuso horário.
        - Parâmetros de entrada do usuário, especificados pelo usuário final em tempo de execução.

    - Defina os elementos do documento necessários e a topologia deles para especificar o formato de um documento final.
    - Configure o fluxo de dados desejado das fontes de dados selecionadas para elementos do documento definido via associações da fonte de dados aos componentes de formato do documento e especifique a lógica de controle de processos.

- Crie um modelo disponível de forma que ele possa ser usado em outras instâncias:

    - Transforme um modelo de documento criado em uma configuração de ER e exporte a configuração da instância atual do aplicativo como um pacote XML que possa ser armazenado localmente ou no Lifecycle Services (LCS).
    - Transforme uma configuração de ER em um modelo de documento do aplicativo.
    - Importe um pacote XML armazenado localmente ou em LCS para a instância atual.

- Personalize o modelo de um documento eletrônico:

    - Traga um modelo de LCS para a instância atual como uma configuração de ER.
    - Crie uma versão personalizada de uma configuração do ER e mantenha uma referência à versão base.

- Integre um modelo a um processo comercial específico, para que ele fique disponível no aplicativo:

    - Defina as configurações para que o aplicativo comece a usar uma configuração de ER ao fazer referência a essa configuração em um parâmetro relacionado ao processo Por exemplo, mencione a configuração de ER em um método Pagamento de contas a pagar específico para gerar uma mensagem de pagamento eletrônico para o processamento de faturas.

- Use um modelo em um processo de negócios específico:

    - Executar uma configuração de ER em um processo comercial específico. Por exemplo, para gerar uma mensagem de pagamento eletrônico para o processamento de faturas quando um método de pagamento que faz referência à configuração de ER é selecionado.

## <a name="concepts"></a>Conceitos
As funções e as atividades relacionadas a seguir estão associadas ao ciclo de vida de configuração de ER.

| Função                                       | Atividades                                                      | descrição |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Consultor funcional de relatório eletrônico | Crie e gerencie componentes de ER (modelos e formatos).           | Um executivo, que projeta modelos de dados específicos de domínio de ER, cria os modelos necessários para documentos eletrônicos e os associa adequadamente. |
| Desenvolvedor de relatório eletrônico             | Crie e gerencie mapeamentos de modelo de dados.                          | Um especialista que seleciona as fontes de dados do Finance necessárias e as associa aos modelos de dados específicos de domínio de ER. |
| Supervisor de contabilidade                      | Defina as configurações relacionadas ao processo que fazem referência a artefatos de ER. | Por exemplo, uma função **Supervisor de contabilidade** que permite que as configurações de uma configuração de ER sejam usadas em um método de pagamento específico de Contas a pagar para gerar uma mensagem do pagamento eletrônico para processar faturas. |
| Auxiliar de pagamentos de contas a pagar            | Use artefatos de ER em um processo de negócios específico.                | Por exemplo, uma função **Auxiliar de pagamentos de contas a pagar** que permite que as mensagens do pagamento eletrônico sejam geradas para processar faturas com base no formato de ER configurado para um método de pagamento específico. |

## <a name="er-configuration-development-lifecycle"></a>Ciclo de vida de desenvolvimento de configuração de ER
Pelos seguintes motivos relacionados a ER, é recomendável projetar configurações de ER no ambiente de desenvolvimento como uma instância separada do Finance and Operations:

- Os usuários nas funções **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico** podem editar configurações e executá-las para fins de teste. Este cenário pode ocasionar chamadas de métodos de classes e de tabelas que podem prejudicar os dados de negócios e o desempenho do uso da instância.
- As chamadas de métodos de classes e de tabelas como fontes de dados de ER das configurações do ER não serão restringidas por pontos de entrada e pelo conteúdo registrado da empresa. Portanto, os dados de negócios confidenciais podem ser acessados pelos usuários que desempenham a função **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico**.

As configurações de ER criadas no ambiente de desenvolvimento podem ser [carregadas](#data-persistence-consideration) no ambiente de teste da avaliação da configuração (integração adequada do processo, exatidão de resultados e desempenho) e do controle de qualidade, como exatidão dos direitos de acesso orientados a funções e diferenciação de direitos. Os recursos que permitem a troca de configuração de ER podem ser usados com essa finalidade. As configurações de ER comprovadas podem ser carregadas no LCS para compartilhá-las com assinantes de serviço ou podem ser [importadas](#data-persistence-consideration) para o ambiente de produção para uso interno.

![Ciclo de vida da configuração de ER.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>Consideração de persistência de dados

Você pode [importar](tasks/er-import-configuration-lifecycle-services.md) individualmente [versões](general-electronic-reporting.md#component-versioning) diferentes de uma [configuração](general-electronic-reporting.md#Configuration) ER para sua instância do Finance. Quando uma nova versão de uma configuração ER é importada, o sistema controla o conteúdo da versão de rascunho dessa configuração:

- Quando a versão importada for anterior à versão mais atual dessa configuração na instância atual do Finance, o conteúdo da versão de rascunho dessa configuração permanecerá inalterado.
- Quando a versão importada for mais atual do que outras versões dessa configuração na instância atual do Finance, o conteúdo da versão importada será copiado para a versão de rascunho dessa configuração para que você continue editando a última versão concluída.

Se essa configuração pertencer ao [provedor](general-electronic-reporting.md#Provider) de configuração ativado no momento, a versão de rascunho dessa configuração ficará visível na FastTab **Versões** da página **Configurações** (**Administração organizacional** > **Relatório eletrônico** > **Configurações**). Você pode selecionar a versão de rascunho da configuração e [modificar](er-quick-start2-customize-report.md#ConfigureDerivedFormat) o conteúdo usando o designer de ER relevante. Após você editar a versão de rascunho de uma configuração ER, o conteúdo não coincidirá mais ao conteúdo da versão mais atual dessa configuração na instância atual do Finance. Para evitar a perda de alterações, o sistema exibe um erro informando que a importação não pode continuar porque a versão dessa configuração é posterior à versão mais atual dessa configuração na instância atual do Finance. Quando isso ocorre, por exemplo, com a configuração de formato **X**, o erro **A versão de formato 'X' não foi concluída** é exibido.

Para desfazer as alterações apresentadas na versão de rascunho, selecione a versão concluída mais atual ou compartilhada da configuração ER no Finance na FastTab **Versões** e, depois, selecione a opção **Obter esta versão**. O conteúdo da versão selecionada é copiado na versão de rascunho.

## <a name="applicability-consideration"></a>Consideração de aplicabilidade

Ao criar uma versão de uma configuração ER, você pode definir sua [dependência](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md) em outros componentes de software. Essa etapa é considerada um pré-requisito para controlar o download desta versão da configuração de um repositório de ER ou um arquivo XML externo, e para qualquer outro uso da versão. Ao tentar importar uma nova versão de uma configuração ER, o sistema usa os pré-requisitos configurados para controlar se a versão pode ser importada.

Em alguns casos, você pode exigir que o sistema ignore os pré-requisitos configurados ao importar novas versões das configurações ER. Para que o sistema ignore os pré-requisitos durante a importação, siga as etapas a seguir.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Defina a opção **Ignorar atualizações de produto e verificação de pré-requisitos de versão durante importação** como **Sim**.

    > [!NOTE]
    > Esse parâmetro é específico do usuário e da empresa.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório Eletrônico (ER)](general-electronic-reporting.md)

[Definir a dependência de configurações ER em outros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
