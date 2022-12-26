---
title: Configurar, importar e verificar documentos XML de NF-e e de DANFE
description: Você pode extrair e importar automaticamente o XML da Nota fiscal Eletrônica (NF-e) e seu DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) de e-mails enviados pelo fornecedor de sua empresa.
author: v-gonode
ms.date: 12/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EFDocumentReceivedXML_BR
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 74b52139722e59f7691b53e8cafbaa9c4fd1a5fd
ms.sourcegitcommit: b55b52b0d49a3bee22fbaef93c3f6ef6941a23cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "9847301"
---
# <a name="set-up-import-and-verify-nf-e-xml-documents-and-danfe"></a>Configurar, importar e verificar documentos XML de NF-e e de DANFE

[!include [banner](../includes/banner.md)]

Você pode extrair e importar automaticamente o XML da Nota fiscal Eletrônica (NF-e) e seu DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) de emails enviados por um fornecedor. O fornecedor deve enviar esses emails como anexos durante o período no qual as mercadorias adquiridas estão em trânsito.

Os seguintes pré-requisitos devem ser atendidos antes de você começar: 
 - Configurar estabelecimentos fiscais na entidade legal. 
 - Configurar parâmetros federais de NF-e, incluindo o código de IBGE selecionado nos parâmetros da autoridade fiscal.
 - Configurar parâmetros de NF-e para estabelecimentos fiscais.

> [!NOTE] 
> Para usar a autenticação moderna a fim de autenticar as conexões ao servidor POP3 para ler emails, conclua as etapas descritas [aqui](/exchange/client-developer/legacy-protocols/how-to-authenticate-an-imap-pop-smtp-application-by-using-oauth) como um pré-requisito para criar um aplicativo do Azure AD. O aplicativo criado terá as permissões de caixa de correio necessárias (POP) para ler emails da caixa de correio compartilhada que você está usando para receber emails enviados por um fornecedor.
> Em seguida, adicione a ID do cliente do aplicativo do Azure AD, o segredo do cliente e as IDs de locatários como segredos a um cofre de chaves no Azure e configure o mesmo no Dynamics 365 Finance.

## <a name="set-up-email-accounts-to-import-xml-files-and-danfe-for-nf-e"></a>Configurar contas de e-mail para importar arquivos XML e DANFE para a NF-e
- Na página **Configurar contas de email**, selecione **Novo** e insira os detalhes da conta.
   - **Endereço do servidor** - Insira o endereço do servidor POP3 para a conta de email.
   - **Porta** - Insira o número da porta a ser usado para o servidor de e-mail.
   - **SSL Necessário** - Marque esta opção para indicar que o servidor requer uma conexão criptografada de (SSL) Secure Socket Layer.
   - **Nome de usuário** - Insira o nome do usuário para a conta de e-mail.
   - **Senha** - Insira a senha da conta de e-mail.

- Para oferecer suporte à autenticação moderna devido à [substituição da autenticação básica no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/deprecation-of-basic-authentication-exchange-online), insira detalhes adicionais.
   - **Usar autenticação moderna** - marque essa caixa de seleção para usar a autenticação moderna baseada em OAuth para conexão com o servidor POP3.
   - **ID do recurso de servidor** - insira o URI do Exchange Server (https://outlook.office.com/ ou https://outlook.office365.com/).
   - **ID do locatário** - insira a referência de certificado do cofre de chaves para a ID de locatário em que o aplicativo do Azure AD com as permissões de caixa de correio necessárias está hospedado.
   - **ID do cliente** - insira a referência de certificado do cofre de chaves para a ID do aplicativo do Azure AD com as permissões de caixa de correio necessárias está hospedado.
   - **Segredo do cliente** - insira a referência de certificado do cofre de chaves para o segredo do cliente do aplicativo do Azure AD.
   - **Autoridade de logon** - insira o URI da autoridade de logon (https://login.microsoftonline.com/).

> [!NOTE] 
> No momento, somente o Exchange Online tem suporte para importar arquivos XML usando autenticação moderna.


## <a name="import-and-verify-the-nf-e-xml-files-and-danfe-from-emails"></a>Importar e verificar os arquivos XML de NF-e e DANFE de e-mails
1. Na página **Importar arquivos XML de email**, se necessário, insira parâmetros, as recorrências, e a agenda de processamento em lotes.
2. Clique em **OK** para importar o XML e os arquivos de DANFE de email recebidos na conta de email.

Os arquivos XML e DANFE importados podem ser exibidos na página **Documentos XML recebidos de NF-e**.
> [!NOTE] 
> Somente o XML de Notas Fiscais Eletrônicas (NF-e) emitido para o CNPJ de estabelecimentos fiscais são importados dos emails.

> [!NOTE] 
> O nome do emissor da Nota fiscal Eletrônica (NF-e) foi deixado em branco quando a ID de registro de impostos (CNPJ) não pode ser encontrada como um atributo de um fornecedor na página **Todos os fornecedores**.

- Para uma Nota Fiscal Eletrônica (NF-e) selecionada, escolha **Documento XML** para exibir o documento XML.
- Para uma Nota Fiscal Eletrônica (NF-e) selecionada, escolha **DANFE** para exibir o Documento Auxiliar da Nota Fiscal Eletrônica (DANFE).
- Para uma Nota fiscal Eletrônica selecionada (NF-e), escolha **Consultar status** para exibir o status da NF-e na SEFAZ usando a chave de status.
  > [!NOTE] 
  > O status, a data, e as horas da consulta são atualizados no Status da SEFAZ e data e hora da última consulta.

## <a name="inquire-about-the-status-of-nf-e-access-keys-at-the-sefaz"></a>Pesquisa sobre o status das teclas de acesso de NF-e no SEFAZ
1. Na página **Consultar status da chave de acesso da NF-e**, no campo **Limite de cancelamento**, insira o número de horas que o fornecedor tem para cancelar a NF-e.
2. No campo **Intervalo mínimo entre as consultas**, insira o intervalo mínimo em minutos entre as consultas da chave de acesso de NF-e recebida na SEFAZ.
3. Se necessário, insira os parâmetros de processamento em lotes, as recorrências e a agenda.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
