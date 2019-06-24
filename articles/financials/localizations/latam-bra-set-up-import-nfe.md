---
title: Configurar, importar e verificar documentos XML de NF-e e de DANFE
description: Você pode extrair e importar automaticamente o XML da Nota fiscal Eletrônica (NF-e) e seu DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) de e-mails enviados pelo fornecedor de sua empresa.
author: v-gonode
manager: AnnBe
ms.date: 06/28/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EFDocumentReceivedXML_BR
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: v-gonode
ms.search.validFrom: ''
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6f4cc45b388e35626a8d98bbf9d2e2ad323de163
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553095"
---
# <a name="set-up-import-and-verify-nf-e-xml-documents-and-danfe"></a>Configurar, importar e verificar documentos XML de NF-e e de DANFE

[!include [banner](../includes/banner.md)]

Você pode extrair e importar automaticamente o XML da Nota fiscal Eletrônica (NF-e) e seu DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) de e-mails enviados pelo fornecedor de sua empresa. O fornecedor deve enviar esses emails como anexos durante o período no qual as mercadorias adquiridas estão em trânsito.

Os seguintes pré-requisitos devem ser atendidos antes de você começar: 
 - Configurar estabelecimentos fiscais na entidade legal. 
 - Configurar parâmetros federais de NF-e, incluindo o código de IBGE selecionado nos parâmetros da autoridade fiscal.
 - Configurar parâmetros de NF-e para estabelecimentos fiscais.

## <a name="set-up-email-accounts-to-import-xml-files-and-danfe-for-nf-e"></a>Configurar contas de e-mail para importar arquivos XML e DANFE para a NF-e
- Na página **Configurar contas de email**, clique em **Novo** e insira os detalhes da conta.
   - **Endereço do servidor** - Insira o endereço do servidor POP3 para a conta de email.
   - **Porta** - Insira o número da porta a ser usado para o servidor de e-mail.
   - **SSL Necessário** - Marque esta opção para indicar que o servidor requer uma conexão criptografada de (SSL) Secure Socket Layer.
   - **Nome de usuário** - Insira o nome do usuário para a conta de e-mail.
   - **Senha** - Insira a senha da conta de e-mail.

## <a name="import-and-verify-the-nf-e-xml-files-and-danfe-from-emails"></a>Importar e verificar os arquivos XML de NF-e e DANFE de e-mails
1. Na página **Importar arquivos XML de email**, se necessário, insira parâmetros, as recorrências, e a agenda de processamento em lotes.
2. Clique em **OK** para importar o XML e os arquivos de DANFE de email recebidos na conta de email.

Os arquivos XML e DANFE importados podem ser exibidos na página **Documentos XML recebidos de NF-e**.
> [!NOTE] 
> Somente o XML de Notas Fiscais Eletrônicas (NF-e) emitido para o CNPJ de estabelecimentos fiscais são importados dos emails.

> [!NOTE] 
> O nome do emissor da Nota fiscal Eletrônica (NF-e) foi deixado em branco quando a ID de registro de impostos (CNPJ) não pode ser encontrada como um atributo de um fornecedor na página **Todos os fornecedores**.

- Para uma Nota fiscal Eletrônica (NF-e) selecionada, clique em **Documento XML** para exibir o documento XML.
- Para uma Nota Fiscal Eletrônica (NF-e) selecionada, clique em **DANFE** para exibir o Documento Auxiliar da Nota Fiscal Eletrônica (DANFE).
- Para uma Nota fiscal Eletrônica selecionada (NF-e), clique em **Consultar status** para consultar o status da NF-e na SEFAZ usando a chave de acesso.
  > [!NOTE] 
  > O status, a data, e as horas da consulta são atualizados no Status da SEFAZ e data e hora da última consulta.

## <a name="inquire-about-the-status-of-nf-e-access-keys-at-the-sefaz"></a>Pesquisa sobre o status das teclas de acesso de NF-e no SEFAZ
1. Na página **Consultar status da chave de acesso da NF-e**, no campo **Limite de cancelamento**, insira o número de horas que o fornecedor tem para cancelar a NF-e.
2. No campo **Intervalo mínimo entre as consultas**, insira o intervalo mínimo entre as consultas em minutos da chave de acesso de NF-e recebida na SEFAZ.
3. Se necessário, insira os parâmetros de processamento em lotes, as recorrências e a agenda.
