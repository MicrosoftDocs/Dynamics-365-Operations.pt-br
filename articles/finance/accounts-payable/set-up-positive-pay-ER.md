---
title: Configurar e gerar arquivos de pagamento positivos usando Relatório eletrônico
description: Este artigo explica como configurar o pagamento positivo usando o Relatório eletrônico.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 491048c7274ba6bb52e0a4b7a6ea5cd0f5ff4741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878208"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Configurar arquivos de pagamento positivos usando o Relatório eletrônico

Este artigo explica como configurar o pagamento positivo e gerar arquivos de pagamento positivo usando relatórios eletrônicos.

> [!NOTE] 
> Antes de usar a função **Gerar arquivo de pagamento positivo do banco**, primeiro você precisará atualizar a lista de entidades.
> Acesse **Gerenciamento de dados > Importação / Exportação > Parâmetros de estrutura** 
> guia rápida **Configurações da entidade**, selecione **Atualizar Lista de Entidades**.


Configure o pagamento positivo para gerar uma lista eletrônica de cheques que é fornecida ao banco. Quando o cheque é apresentado ao banco, o banco o compara à lista de cheques. Se o cheque corresponder a um cheque na lista, o banco o liberará. Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.

## <a name="security-for-positive-pay-files"></a>Segurança para arquivos de pagamento positivo
Os arquivos de pagamento positivo podem conter dados sigilosos sobre o credor e valores de cheque. Portanto, certifique-se de usar medidas de segurança apropriadas a partir do momento em que os arquivos são geradas até o momento em que são recebidos pelo banco. Os arquivos de pagamento positivo são baixados para o local especificado pelo navegador. Como os arquivos de pagamento positivo podem conter dados sigilosos, é importante que somente os usuários autorizados tenham acesso para gerar e exibir as informações no Microsoft Dynamics 365 Finance. Use a tabela a seguir para ajudar a determinar os privilégios necessários.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarefa</th>
<th>Privilégio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Gere arquivos de pagamento positivo na página de listagem <strong>Contas bancárias</strong> ou na página <strong>Contas bancárias</strong>.</td>
<td><ul>
<li><strong>Manter informações de pagamento positivo do banco</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Gere arquivos de pagamento positivo para várias entidades legais e contas bancárias na página <strong>Gerar um arquivo de pagamento positivo</strong>.</td>
<td><ul>
<li><strong>Manter informações de pagamento positivo do banco</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Exiba os arquivos de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</td>
<td><strong>Exibir informações de pagamento positivo bancário para várias entidades legais</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Confirme um arquivo de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</td>
<td><strong>Confirmar arquivo de pagamento positivo</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Cancele um arquivo de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</td>
<td><strong>Cancelar arquivo de pagamento positivo</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-the-electronic-reporting-configuration"></a>Definir a configuração do Relatório eletrônico

1. Acesse **Espaços de trabalho \> Relatório eletrônico**.
2. No bloco do provedor de configuração da **Microsoft**, selecione **Repositórios**.
3. Selecione **Global** e, em seguida, selecione **Abrir**.
4. Se for necessário estabelecer uma conexão com o repositório, selecione o link azul na caixa de diálogo.
5. Na lista de configuração, localize e selecione o **formato de pagamento positivo \> do modelo de pagamento positivo**.
6. Na FastTab **Versões**, selecione a versão mais recente e depois **Importar**.

## <a name="set-up-a-positive-pay-format"></a>Configurar um formato de pagamento positivo

1. Acesse **Gerenciamento de caixa e bancos \> Configuração \> Formatos de pagamento positivo**.
2. Selecione **Novo**.
3. Defina os campos **Formato de pagamento** e **Descrição**.
4. Marque a caixa de seleção **Formato de exportação eletrônico genérico**.
5. Defina o campo **Exportar configuração de formato** como **Formato de pagamento positivo**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Atribuir um formato de pagamento positivo a uma conta bancária
Para cada conta bancária que você deseja gerar as informações de pagamento positivo, é necessário atribuir o formato de pagamento positivo que foi especificado na seção anterior. Na página Contas bancárias, selecione o formato de pagamento positivo que corresponda à conta bancária. No campo **Data inicial do pagamento positivo**, insira a primeira data para gerar os arquivos de pagamento positivo. 

>[!Important]
> Insira uma data no campo **Data inicial do pagamento positivo**. Se deixado em branco, o primeiro arquivo de pagamento positivo gerado incluirá todos os cheques que foram criados para esta conta bancária.

1. Acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Abra a conta bancária.
3. Na FastTab **Geral**, defina o campo **Formato de pagamento positivo** como o formato que foi criado anteriormente.
4. Defina o campo **Data de início do pagamento positivo** como a data atual.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Atribuir uma sequência numérica para arquivos de pagamento positivo
Cada arquivo de pagamento positivo deve ter um número exclusivo. Na página **Parâmetros de gerenciamento de caixa e bancos**, crie uma sequência numérica para arquivos de pagamento positivo na guia **Número de sequências**.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Gerar um arquivo de pagamento positivo para uma única conta bancária
Você pode gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária. Para obter informações sobre como gerar arquivos de pagamento positivo para várias entidades legais e contas bancárias ao mesmo tempo, consulte a próxima seção. Para gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária, abra a caixa de diálogo **Gerar um arquivo de pagamento positivo** na página **Contas bancárias**. No campo **Data de fechamento**, insira a data do último cheque a ser incluído no arquivo de pagamento positivo. Todos os cheques que não tiverem sido incluídos em um arquivo de pagamento positivo até o final dessa data de verificação serão incluídos no arquivo.

1. Acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Abra uma conta bancária para a qual o pagamento positivo está configurado.
3. Selecione **Gerenciar pagamentos \> Pagamento positivo \> Arquivo de pagamento positivo**.
4. Defina o campo **Data de fechamento**. Os cheques que foram gerados antes dessa data serão incluídos.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Gerar um arquivo de pagamento positivo para várias contas bancárias
Para gerar um arquivo de pagamento positivo para várias contas bancárias, use a tarefa periódica **Arquivo de pagamento positivo**. Selecione o formato de pagamento positivo para o arquivo e especifique se deseja gerar o arquivo de pagamento positivo para todas as entidades legais ou para uma entidade legal selecionada. Você também pode gerar o arquivo de pagamento positivo para todas as contas bancárias que usam o formato de pagamento positivo para uma conta bancária selecionada. No campo **Data de fechamento**, insira a data do último cheque a ser incluído no arquivo de pagamento positivo. Todos os cheques que não tiverem sido incluídos em um arquivo de pagamento positivo até o final dessa data de verificação serão incluídos no arquivo.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Exibir os resultados de geração de um arquivo de pagamento positivo
Depois que o arquivo positivo de pagamento for gerado, você poderá exibir os resultados na página **Resumo do arquivo de pagamento positivo**. Para exibir os detalhes dos cheques individuais, vá para a página **Detalhes do arquivo de pagamento positivo**.

## <a name="confirm-a-positive-pay-file"></a>Confirmar um arquivo de pagamento positivo
Depois que os cheques listados em um arquivo de pagamento positivo forem pagos, você receberá um número de confirmação do banco. Em seguida, será possível confirmar o arquivo de pagamento positivo.. Na página **Resumo do arquivo de pagamento positivo**, selecione um arquivo de pagamento positivo com o status **Criado** e selecione a ação **Inserir confirmação**. Quando você confirma um arquivo de pagamento positivo, o número de confirmação recebido do banco é registrado.

## <a name="recall-a-positive-pay-file"></a>Cancelar um arquivo de pagamento positivo
Se você tiver de alterar um arquivo de pagamento positivo, poderá cancelá-lo. Na página **Resumo do arquivo de pagamento positivo**, selecione um arquivo de pagamento positivo com o status **Criado** e selecione a ação **Cancelar**. Para cada cheque no arquivo de pagamento positivo, o campo que indica se esse cheque foi incluído em um arquivo de pagamento positivo será redefinido. Em seguida, você poderá criar um novo arquivo de pagamento positivo que inclua o cheque cancelado.


O arquivo XML resultante será baixado.
