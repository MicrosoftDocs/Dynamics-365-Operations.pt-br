---
title: Relatórios duplos
description: Este tópico apresenta um exemplo que mostra como você pode cumprir os requisitos de relatório do Financial Reporting Standard (IFRS) e relatórios estatutários em arrendamento de ativos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a7d9b3ea3d4f1d48b8a7326bd5a01d3119310c62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003172"
---
# <a name="dual-reporting"></a>Relatórios duplos

[!include [banner](../includes/banner.md)]

Este tópico apresenta um exemplo que mostra como você pode cumprir os requisitos de relatório do Financial Reporting Standard (IFRS) e relatórios estatutários em arrendamento de ativos. A familiaridade com lançamentos de camadas no Microsoft Dynamics 365 Finance é necessária e facilitará o entendimento do exemplo.

## <a name="example"></a>Exemplo

O exemplo a seguir conta um arrendamento no relatório estatutário italiano usando o método de base de caixa e o modo de relatório do IFRS. A empresa deve estabelecer três registros para cumprir os requisitos legais da Itália e os requisitos do IFRS 16. Um registro é necessário para o IFRS 16, outro é necessário para os requisitos estatutários e outro é necessário para reverter automaticamente lançamentos estatutários. Os registros são configurados conforme mostrado nas tabelas a seguir.

**Registro IFRS 16**

O livro IFRS 16 é configurado de forma que ele cumpra com o padrão de contabilidade IFRS 16. Todas as entradas lançadas neste manual serão lançadas em uma camada personalizada.

| Organização                                    | descrição    |
|-----------------------------------------|----------------|
| Tipo de livro                               | IFRS 16        |
| Descrição do registro                        | IFRS 16        |
| Nível de Lançamento                           | Camada personalizada 1 |
| Tipo de arrendamento                              | Finance        |
| Estrutura contábil                    | IFRS 16        |
| Configuração de prazo do arrendamento / vida útil         | 0,00           |
| Configuração de valor presente / valor justo do ativo | 0,00           |
| Limite de curto prazo                    | 12             |
| Limite de valor baixo                     | 5.000,00       |
| Pagar ao fornecedor                           | Não             |

**Livro fiscal**

O livro fiscal é um registro de base de caixa em que a empresa contará com as despesas de arrendamento como o valor de pagamento à vista pago mensalmente por aluguel. Esse registro não produzirá um ativo de direito de uso (DDU) ou uma responsabilidade de arrendamento.

| Organização                                    | descrição |
|-----------------------------------------|-------------|
| Tipo de livro                               | Fiscal   |
| Descrição do registro                        | GAAP Local  |
| Nível de Lançamento                           | Atual     |
| Tipo de arrendamento                              | Automática   |
| Estrutura contábil                    | Base de pagamento à vista  |
| Configuração de prazo do arrendamento / vida útil         | 0,00        |
| Configuração de valor presente / valor justo do ativo | 0,00        |
| Limite de curto prazo                    | 0           |
| Limite de valor baixo                     | 0           |
| Pagar ao fornecedor                           | Não          |

**Livro de estorno fiscal**

O livro de estorno fiscal é configurado da mesma forma que o livro fiscal.

| Organização                                    | descrição                    |
|-----------------------------------------|--------------------------------|
| Tipo de livro                               | Fiscal - Estorno           |
| Descrição do registro                        | Registro para reverter o livro fiscal |
| Nível de Lançamento                           | Camada personalizada 1                 |
| Tipo de arrendamento                              | Automática                      |
| Estrutura contábil                    | Base de pagamento à vista                     |
| Configuração de prazo do arrendamento / vida útil         | 0,00                           |
| Configuração de valor presente / valor justo do ativo | 0,00                           |
| Limite de curto prazo                    | 0                              |
| Limite de valor baixo                     | 0                              |
| Pagar ao fornecedor                           | Não                             |

Neste exemplo, um arrendamento foi criado com as seguintes configurações nas guias **Geral** **Linhas de agendamento de pagamento**.

**Guia Geral**

| Campo                      | Alíquota            |
|----------------------------|------------------|
| Taxa incremental de empréstimo | 5%               |
| Data de início          | 1/1/2020         |
| Grupo de arrendamento                | Instalações        |
| Fornecedor                     | 1001             |
| Valor justo do ativo    | 245,000          |
| Vida útil do ativo          | 120              |
| Tipo de anuidade               | Anuidade comum |
| Intervalo de composição       | Mensalmente          |

**Guia Linhas de agenda de pagamento**

| Campo             | Alíquota      |
|-------------------|------------|
| Data inicial        | 1/1/2020   |
| Intervalo do período   | Meses     |
| Períodos           | 24         |
| Data de término          | 31/12/2020 |
| Frequência de pagamento | Mensalmente    |
| Valor do pagamento    | 1.000      |

Para considerar esse arrendamento em duas estruturas, use um nível de lançamento atual e um nível de lançamento personalizado. A tabela a seguir mostra um exemplo de cada entrada de diário que represente razoavelmente as finanças sob cada padrão de relatório. Posteriormente, é fornecida uma descrição detalhada de cada entrada de diário para o primeiro mês do arrendamento.

<table>
<thead>
<tr>
<th rowspan='3'>Número da conta</th>
<th rowspan='3'>descrição</th>
<th colspan='3'>Livro fiscal (nível atual)</th>
<th rowspan='3'>Total do nível atual</th>
<th>Registro de estorno (nível personalizado)</th>
<th colspan='4'>Registro IFRS 16 (nível personalizado)</th>
<th rowspan='3'>Nível atual + total do nível personalizado</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
<th>JE-130</th>
<th>JE-140</th>
<th>JE-150</th>
<th>JE-160</th>
<th>JE-170</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Despesa de arrendamento</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
<td>-1.000,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>2</td>
<td>Tarifa bancária</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Despesa IVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Conta de compensação</td>
<td>-1.000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
<td>1,000.00</td>
<td></td>
<td>-1.000,00</td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Contas a Pagar</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Ativo DDU</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>22,794.00</td>
<td></td>
<td></td>
<td></td>
<td>22,793.90</td>
</tr>
<tr>
<td>7</td>
<td>Obrigação de arrendamento mercantil</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>-22.794,00</td>
<td>1,000.00</td>
<td>-94,97</td>
<td></td>
<td>-21.888,87</td>
</tr>
<tr>
<td>8</td>
<td>Despesa de Juros</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td>94.97</td>
<td></td>
<td>94.97</td>
</tr>
<tr>
<td>9</td>
<td>Pagamento à vista</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Despesa de Depreciação</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>949,75</td>
<td>949,75</td>
</tr>
<tr>
<td>11</td>
<td>Depreciação Acumulada</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-949,75</td>
<td>-949,75</td>
</tr>
</tbody>
</table>

Como mostra a tabela acima, é necessário reportar três registros em relatórios fiscais e em relatórios IFRS.

- O livro fiscal registra o pagamento do arrendamento de acordo com as regras para a contabilidade de base de caixa no nível atual.
- O registro de estorno fiscal inverte as entradas do diário fiscal.
- O registro IFRS 16 cria as entradas de diário requeridas pelo IFRS 16.

É necessário inserir um arrendamento somente uma vez. Em seguida, você poderá abrir a página **Registros** para ver todos os registros associados ao arrendamento.

> [!NOTE]
> Quando você cria os registros, todos os três devem ser associados ao mesmo registro de arrendamento.

A primeira entrada de diário registra a despesa de arrendamento mediante o livro fiscal. Você pode criar os pagamentos em um lote ou selecionando o plano de pagamento no livro fiscal.

Neste exemplo, a entrada de diário a seguir é criada para o livro fiscal no plano de pagamento.

### <a name="lease-payment--1312020--je-100"></a>Pagamento de arrendamento – 31/1/2020 – JE 100

| Tipo de conta | Número da conta | Camada   | Descrição da conta | Débito    | Crédito   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 1              | Atual | Despesa de arrendamento       | 1,000.00 |          |
| Ledger       | 4              | Atual | Conta de compensação    |          | 1,000.00 |

Um auxiliar de contas a pagar usa a funcionalidade padrão do Dynamics 365 para criar uma fatura a pagar para o arrendamento fora do Arrendamento de ativos. No entanto, em vez de selecionar **Despesa de arrendamento** como a conta de débito, o auxiliar de contas a pagar seleciona uma conta de compensação para gerar a entrada a seguir.

### <a name="ap-process--1312020--je-110"></a>Processo de AP - 31/1/2020 – JE 110

| Tipo de conta | Número da conta | Camada   | Descrição da conta | Débito    | Crédito   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 4              | Atual | Conta de compensação    | 1,000.00 |          |
| Ledger       | 2              | Atual | Tarifa bancária            | 3.00     |          |
| Ledger       | 3              | Atual | Despesa IVA         | 5.00     |          |
| Fornecedor       | 5              | Atual | Contas a Pagar    |          | 1,008.00 |

Quando a instrução for emitida para o fornecedor, você seguirá o processo de pagamento regular. Durante esse processo, a entrada de diário a seguir é gerada.

### <a name="cash-payment--1312020--je-120"></a>Pagamento à vista – 31/1/2020 – JE 120

| Tipo de conta | Número da conta | Camada   | Descrição da conta | Débito    | Crédito   |
|--------------|----------------|---------|---------------------|----------|----------|
| Fornecedor       | 5              | Atual | Contas a Pagar    | 1,008.00 |          |
| Banco         | 9              | Atual | Pagamento à vista                |          | 1,008.00 |

Nessa situação, você cumpriu a conformidade total desse arrendamento mediante os requisitos de relatórios estatutários e pode gerar um balancete usando o nível atual. O sistema retorna um balancete que tem os seguintes números.

<table>
<thead>
<tr>
<th rowspan='3'>Número da conta</th>
<th rowspan='3'>descrição</th>
<th colspan='3'>Livro fiscal (nível atual)</th>
<th rowspan='3'>Total do nível atual</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Despesa de arrendamento</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
</tr>
<tr>
<td>2</td>
<td>Tarifa bancária</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Despesa IVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Conta de compensação</td>
<td>-1.000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Contas a Pagar</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Ativo DDU</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>7</td>
<td>Obrigação de arrendamento mercantil</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>8</td>
<td>Despesa de Juros</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>9</td>
<td>Pagamento à vista</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Despesa de Depreciação</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>11</td>
<td>Depreciação Acumulada</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
</tbody>
</table>

Se você quiser usar os números do IFRS 16 para executar o mesmo balancete, as entradas do diário contábil fiscal devem ser revertidas, e as entradas de diário de IFRS 16 devem ser lançadas. Para reverter as entradas de diário estatutário, este exemplo inclui um registro de estorno estatutário que tem a mesma configuração que o livro fiscal, mas um perfil de lançamentos oposto. Por exemplo, o livro fiscal *debitou* uma conta de despesas de arrendamento, mas o livro de estorno *creditará* essa conta. Esses relacionamentos são facilmente definidos nas contas de lançamento de arrendamento de ativos na página **Parâmetros de arrendamento de ativos** (**Arrendamento de ativos \> Configuração \> Parâmetros de arrendamento de ativos**).

Quando o mesmo processo usado para o livro fiscal é usado para o livro de estorno, a entrada de diário a seguir é criada. A diferença é que o registro de estorno lista as entradas invertidas do registro fiscal. As entradas de estorno também são feitas no nível personalizado. Quando um balancete é executado no nível atual, as entradas do diário de estorno não são incluídas.

### <a name="lease-payment--1312020--je-130"></a>Pagamento de arrendamento – 31/1/2020 – JE 130

| Tipo de conta | Número da conta | Camada  | Descrição da conta | Débito    | Crédito   |
|--------------|----------------|--------|---------------------|----------|----------|
| Ledger       | 4              | Personalizada | Conta de compensação    | 1,000.00 |          |
| Ledger       | 1              | Personalizada | Despesa de arrendamento       |          | 1,000.00 |

Agora que você eliminou as entradas fiscais de diário, todas as entradas de diário que o IFRS 16 requer no registro IFRS 16 são registradas. Essas entradas incluem o reconhecimento inicial do ativo DDU e a responsabilidade, bem como o registro de juros e depreciação.

### <a name="initial-recognition--112020--je-140"></a>Reconhecimento inicial – 1/1/2020 – JE 140

| Tipo de conta | Número da conta | Camada  | Descrição da conta      | Débito     | Crédito    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| Ledger       | 6              | Personalizada | Ativo DDU                | 22,793.90 |           |
| Ledger       | 7              | Personalizada | Obrigação de arrendamento mercantil |           | 22,793.90 |

O pagamento do arrendamento é lançado como os outros pagamentos de arrendamento. O motivo de usar a conta de compensação é garantir que o dinheiro seja creditado apenas uma vez.

### <a name="lease-payment--1312020--je-150"></a>Pagamento de arrendamento – 31/1/2020 – JE 150

| Tipo de conta | Número da conta | Camada  | Descrição da conta      | Débito    | Crédito   |
|--------------|----------------|--------|--------------------------|----------|----------|
| Ledger       | 7              | Personalizada | Obrigação de arrendamento mercantil | 1,000.00 |          |
| Ledger       | 4              | Personalizada | Conta de compensação         |          | 1,000.00 |

A entrada do diário de despesas de juros é gerada a partir do agendamento de amortização de passivo.

### <a name="interest-expense--1312020--je-160"></a>Despesa de Juros – 31/1/2020 – JE 160

| Tipo de conta | Número da conta | Camada  | Descrição da conta      | Débito | Crédito |
|--------------|----------------|--------|--------------------------|-------|--------|
| Ledger       | 8              | Personalizada | Despesa de Juros         | 94.97 |        |
| Ledger       | 7              | Personalizada | Obrigação de arrendamento mercantil |       | 94.97  |

A entrada do diário de despesas de depreciação é gerada a partir do agendamento de depreciação de ativos.

### <a name="depreciation-expense--1312020--je-170"></a>Despesa de depreciação – 31/1/2020 – JE 170

| Tipo de conta | Número da conta | Camada  | Descrição da conta      | Débito  | Crédito |
|--------------|----------------|--------|--------------------------|--------|--------|
| Ledger       | 10             | Personalizada | Despesa de Depreciação     | 949,75 |        |
| Ledger       | 11             | Personalizada | Depreciação Acumulada |        | 949,75 |

Depois que todas essas entradas de diário forem criadas e lançadas, você verá os seguintes valores de "nível 1 personalizado". Observe que a última coluna inclui a tarifa bancária, a despesa de imposto sobre valor agregado (IVA) e a redução de pagamento à vista do nível anterior, mas ela não inclui as entradas de diário de relatório estatutário. Portanto, você realmente obtém recursos de relatório duplo. Neste ponto, a empresa precisa apenas executar seu balancete e combinar o nível atual e o nível personalizado para criar um balancete de IFRS.

| Nº de conta | descrição              | Livro fiscal\-Nível atual\-JE\-100\-Dr \(Cr\) | Livro fiscal\-Nível atual\-JE\-110\-Dr \(Cr\) | Livro fiscal\-Nível atual\-JE\-120\-Dr \(Cr\) | Nível atual \- Totais | - | Registro de estorno\-Nível atual\-JE\-130\-Dr \(Cr\) | Registro IFRS 16\-Nível atual\-JE\-140\-Dr \(Cr\) | Registro IFRS 16\-Nível atual\-JE\-150\-Dr \(Cr\) | Registro IFRS 16\-Nível atual\-JE\-160\-Dr \(Cr\) | Registro IFRS 16\-Nível atual\-JE\-170\-Dr \(Cr\) | Nível personalizado \+ Nível atual \- Totais |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| 1          | Despesa de arrendamento            | 1,000\,00                                         |                                                   |                                                   | 1,000\,00               |   | \-1.000                                         |                                                |                                                |                                                |                                                | 0\,00                                   |
| 2          | Tarifa bancária                 |                                                   | 3\,00                                             |                                                   | 3\,00                   |   |                                                 |                                                |                                                |                                                |                                                | 3\,00                                   |
| 3          | Despesa de IVA              |                                                   | 5\,00                                             |                                                   | 5\,00                   |   |                                                 |                                                |                                                |                                                |                                                | 5\,00                                   |
| 4          | Conta de compensação         | \-1.000\,00                                       | 1,000\,00                                         |                                                   | 0\,00                   |   | 1.000                                           |                                                | \-1.000                                        |                                                |                                                | 0\,00                                   |
| 5          | Contas a Pagar         |                                                   | \-1.008\,00                                       | 1,008\,00                                         | 0\,00                   |   |                                                 |                                                |                                                |                                                |                                                | 0\,00                                   |
| 6          | Ativo DDU                |                                                   |                                                   |                                                   | 0\,00                   |   |                                                 | 22.794                                         |                                                |                                                |                                                | 22.793\,90                              |
| 7          | Obrigação de arrendamento mercantil |                                                   |                                                   |                                                   | 0\,00                   |   |                                                 | \-22.794                                       | 1.000                                          | \-94\,97                                       |                                                | \-21.888\,87                            |
| 8          | Despesa de Juros         |                                                   |                                                   |                                                   | 0\,00                   |   |                                                 |                                                |                                                | 94\,97                                         |                                                | 94\,97                                  |
| 9          | Pagamento à vista                     |                                                   |                                                   | \-1.008\,00                                       | \-1.008\,00             |   |                                                 |                                                |                                                |                                                |                                                | \-1.008\,00                             |
| 10         | Despesa de Depreciação     |                                                   |                                                   |                                                   | 0\,00                   |   |                                                 |                                                |                                                |                                                | 949\,75                                        | 949\,75                                 |
| 11         | Depreciação Acumulada |                                                   |                                                   |                                                   | 0\,00                   |   |                                                 |                                                |                                                |                                                | \-949\,75                                      | \-949\,75                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]