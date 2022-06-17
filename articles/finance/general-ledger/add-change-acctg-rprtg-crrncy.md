---
title: Alterar a moeda de relatório ou contábil
description: Este artigo explica como alterar a moeda de relatório ou contábil, ou adicionar uma moeda de relatório à configuração de um razão.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b02432c8e0bdf52c2a588f67a581b78e682b1bf8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904604"
---
# <a name="change-the-accounting-or-reporting-currency"></a>Alterar a moeda de relatório ou contábil

[!include [banner](../includes/banner.md)]

Este artigo explica como alterar a moeda de relatório ou contábil, ou adicionar uma moeda de relatório à configuração de um razão.

## <a name="symptom"></a>Sintoma

Você deseja alterar a moeda de relatório ou contábil, ou adicionar uma moeda de relatório à configuração do razão. Isso geralmente ocorre nos seguintes cenários:

- A moeda de relatório ou contábil incorreta foi especificada quando uma entidade legal foi configurada. Agora, você deseja alterar essa moeda.
- Uma moeda de relatório foi especificada quando uma entidade legal foi configurada, mas a organização agora deseja remover a moeda de relatório.
- A organização está atualizando ou migrando para o Microsoft Dynamics 365 Finance e deseja alterar a moeda de relatório ou contábil.

Uma organização que não utilizou anteriormente o recurso de moeda dupla deseja começar a usá-lo. Esse problema geralmente ocorre nos seguintes cenários:

- Nenhuma moeda de relatório foi especificada quando uma entidade legal foi configurada. (A moeda de relatório é opcional.) Agora, você deseja adicionar uma moeda de relatório.

## <a name="resolution"></a>Resolução

A consideração mais importante é se alguma transação (real ou de orçamento) foi lançada na entidade legal para a configuração do razão. **Não é possível alterar a moeda de relatório ou contábil, ou adicionar uma moeda de relatório, caso alguma transação (real ou de orçamento) tenha sido lançada na entidade legal.** Siga as etapas em uma das seguintes seções, dependendo se as transações tiverem sido lançadas.

### <a name="no-transactions-have-been-posted"></a>Nenhuma transação foi lançada

1. Na entidade legal para a qual você está atualizando as moedas, acesse **Contabilidade \> Configuração do razão \> Razão**.
2. Na página **Razão**, selecione **Editar**.
3. Na Guia Rápida **Moeda**, selecione a moeda contábil e a moeda de relatório a ser usada para a entidade legal.
4. Selecione **Salvar**.

Se os campos para a moeda contábil e a moeda de relatório não estiverem disponíveis na página **Razão**, uma ou mais transações (real ou de orçamento) foram lançadas na entidade legal. Portanto, as moedas não poderão ser alteradas. Nesse caso, siga as etapas na próxima seção.

### <a name="transactions-have-been-posted"></a>Transações foram lançadas

**Se houver transações lançadas na entidade legal, a única maneira de alterar ou adicionar moedas contábeis e de relatório é criar uma nova entidade legal com as moedas corretas.** Para ajudar a tornar esse processo mais fácil, o Gerenciamento de dados no sistema permite copiar registros de configuração e registros mestre da entidade legal atual para uma nova entidade legal.

As alterações nas moedas contábeis e de relatório são dominantes. Elas afetam não só a contabilidade, mas também todos os razão auxiliares (Contas a receber, Contas a pagar, Estoque, Projeto, etc.), todas as soluções de fornecedores independentes de software (ISV) e qualquer extensão que você tenha feito que armazene valores.

O processo de encontrar e traduzir cada valor para uma moeda diferente está sujeito a erro. Portanto, a equipe de engenharia não aprova um script que altera ou adiciona moedas contábeis e de relatório. Além disso, embora houvesse uma ferramenta disponível para o Microsoft Dynamics AX 2012 que permitia alterar ou adicionar moedas contábeis e de relatório, essa ferramenta foi preterida para o AX 2012 R3 e para o Finance.

Siga estas etapas para copiar os dados de configuração e os dados mestre da entidade legal atual para uma nova entidade legal.

1. Acesse **Espaços de trabalho \> Gerenciamento de dados**.
2. Selecione **Modelos** no grupo **Importar/Exportar**.
3. Verifique se os modelos estão disponíveis. Se nenhum modelo estiver disponível, selecione **Carregar modelos padrão** e aguarde até que os modelos sejam gerados.
4. Retorne ao espaço de trabalho **Gerenciamento de dados**.
5. Selecione **Copiar na entidade legal**.
6. Insira um nome e uma descrição para o grupo.
7. No campo **Entidade legal de origem**, selecione a entidade legal da qual os dados serão copiados.
8. Na Guia Rápida **Entidades legais de destino**, selecione **Criar entidades legais** para criar uma entidade legal para a qual você pode copiar os dados da entidade legal de origem. Selecione **Selecionar existente** para copiar os dados em uma entidade legal existente.
9. Opcional: defina o campo **Copiar sequências numéricas** como **Sim**. (Essa etapa é recomendável quando você copia dados.)
10. Na área **Entidades selecionadas**, selecione **Adicionar modelo**.
11. Selecione os modelos a serem usados. Os modelos sugeridos para uma nova entidade legal incluem **025 – Contabilidade** e **Finanças**. Recomendamos que você examine todos os outros modelos disponíveis para determinar se algum deles se aplica a seus requisitos.
12. Selecione **Copiar na entidade legal** para iniciar um processo em lote que criará as entidades selecionadas e as copiará para a entidade legal de destino.
13. Depois que o processo for concluído, mas antes que qualquer transação seja lançada, acesse o razão e atualize as moedas contábeis e de relatório, conforme descrito anteriormente neste artigo.

Se você criou uma entidade legal para que pudesse alterar a moeda de relatório ou contábil, verifique se os saldos iniciais foram traduzidos das moedas da entidade legal antiga para as novas moedas.

Para assistir a um vídeo que mostra as etapas anteriores, consulte [Copiar na entidade legal](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).
