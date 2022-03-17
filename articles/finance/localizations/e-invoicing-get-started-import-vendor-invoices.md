---
title: Usar o serviço de faturamento eletrônico para importar faturas de fornecedor
description: Este tópico fornece informações sobre como importar faturas de fornecedor usando o serviço de Faturamento eletrônico.
author: gionoder
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c28adbfe532e77a52cab7625b9539d1e8e528bea
ms.sourcegitcommit: 19f0e69a131e9e4ff680eac13efa51b04ad55a38
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2022
ms.locfileid: "7983814"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Usar o serviço de faturamento eletrônico para importar faturas de fornecedor

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tópico fornece informações que ajudarão você na introdução às faturas de vendedor de importação usando o serviço de Faturamento eletrônico. Ele guia você pelas etapas de configuração no Regulatory Configuration Services (RCS), Dynamics 365 Finance e Dynamics 365 Supply Chain Management que você precisa seguir para receber faturas eletrônicas dos fornecedores.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Configurar importação de fatura de fornecedor no RCS
Para configurar a importação de fatura de fornecedor no RCS, siga estas etapas:

1. Consulte a lista de [recursos de Faturamento eletrônico em disponibilidade geral](e-invoicing-configuration-rcs.md#generally-available-features).
2. Selecione e importe o recurso de Faturamento eletrônico criado por você. Para obter mais informações, consulte [Importar um recurso de Faturamento eletrônico do provedor de configuração da Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Crie um recurso Faturamento eletrônico para sua organização. Para obter mais informações, consulte [Criar um recurso de Faturamento eletrônico abaixo do provedor da sua organização](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>Configurar um canal de conta de email

Configure um canal de conta de email se o recurso de Faturamento eletrônico criado importar faturas eletrônicas de fornecedor de arquivos anexos recebidos por email.

1. No RCS, selecione o recurso de Faturamento eletrônico criado por você. Certifique-se de selecionar a versão com o status de **Rascunho**.
2. Na guia **Configurações**, na grade, selecione uma configuração de recurso e, em seguida, **Editar**.
3. Na guia **Canal de dados** no grupo de campos **Parâmetros**, no campo **Canal de dados**, insira o nome do canal. O nome do canal não deve ter mais de dez caracteres.
4. No campo **Endereço do servidor**, insira provedor da conta de email. Por exemplo, o endereço do servidor para **https://outlook.live.com/** é **imap-mail.outlook.com**.
5. No campo **Porta do servidor**, insira a porta usada pelo provedor da conta de email. Por exemplo, a porta do servidor para **https://outlook.live.com/** é **993**.
6. No campo **Segredo do nome de usuário**, insira o nome do segredo do Key Vault que contém a ID da conta de usuário de email. Esse segredo deve ser criado no Azure Key Vault e configurado no seu ambiente de serviço. 
7. No campo **Segredo da senha do usuário**, insira o nome do segredo do Key Vault que contém a senha da conta de usuário de email.
8. Opcional – insira os valores nos campos **Filtro de remetente**, **Filtro de assunto** e **Filtro de data**.
9. Insira os nomes das pastas de caixa de correio nas quais as mensagens serão:

    - Importadas de: **Pasta principal**
    - Salvas após processamento bem-sucedido: **Pasta de arquivo**
    - Salvas após processamento sem êxito: **Pasta de erros** Não é necessário criar essas pastas na caixa de email. As pastas são criadas automaticamente após a importação e o processamento da primeira fatura eletrônica. 
   
10. No grupo de campos **Filtro de anexos**, adicione as informações de filtragem de arquivos. Somente anexos que satisfaçam ao filtro definido são processados. Por exemplo, você pode configurar "\*.xml" para anexos com uma extensão XML. O nome do anexo é usado no Dynamics 365 Finance ou no Dynamics 365 Supply Chain Management durante a instalação. 
11. Na guia **Regras de aplicabilidade**, revise e atualize os critérios, conforme necessário. O campo **Canal** deve ser igual ao **Canal de dados** fornecido anteriormente. Para obter mais informações, consulte [Regras de aplicabilidade](e-invoicing-configuration-rcs.md#applicability-rules).
12. Selecione **Salvar** e feche a página.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Configurar um canal do Microsoft SharePoint

Configure um canal do Microsoft SharePoint se o recurso de Faturamento eletrônico importar faturas eletrônicas de fornecedor de arquivos colocados em pastas do SharePoint.

1. No RCS, selecione o recurso de Faturamento eletrônico criado por você. Certifique-se de selecionar a **Versão** com o status de **Rascunho**.
2. Na guia **Configurações**, na grade, selecione uma configuração de Recurso e, em seguida, **Editar**.
3. Na guia **Canal de dados**, no grupo de campos **Parâmetros**, selecione **Endereço do SharePoint** e insira a URL do SharePoint.
4. Selecione **Porta do servidor** e insira a porta usada pelo provedor da conta de email.
5. Selecione **ID do aplicativo** e insira o nome do segredo do Key Vault que contém a ID do cliente do SharePoint.
6. Selecione **Segredo do aplicativo** e insira o nome do segredo do Key Vault que contém a senha do cliente do SharePoint.
7. Selecione **Filtro de arquivo**. Revise e atualize a máscara para filtrar os arquivos que contêm a fatura eletrônica de fornecedor a ser importada.
8. Na guia **Regras de aplicabilidade**, revise e atualize os critérios, se necessário. Para obter mais informações, consulte [Regras de aplicabilidade](e-invoicing-configuration-rcs.md#applicability-rules).
9. Selecione **Salvar** e feche a página

### <a name="deploy-an-electronic-invoicing-feature"></a>Implantar um recurso Faturamento eletrônico

Para implantar o recurso Faturamento eletrônico, consulte [Implantar o recurso Faturamento eletrônico ao Ambiente de serviço](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Configurar a importação da fatura de fornecedor no Finance ou no Supply Chain Management
Conclua as etapas nas duas seções a seguir para configurar diferentes tipos de importação de fatura de fornecedor.

### <a name="import-brazilian-nf-e-from-email"></a>Importar NF-e brasileira de email

1. Entre no ambiente do Finance ou do Supply Chain Management e verifique se você está na entidade legal correta.
2. Acesse **Administração da organização** > **Configuração** > **Parâmetros de documentos eletrônicos**.
3. Na guia **Recursos**, verifique se **NF-e Federal – nota fiscal eletrônica brasileira** está selecionada.
4. Na guia **Canais externos**, no grupo de campos **Canais**, selecione **Adicionar**.
5. No campo **Canal**, insira **NFe** (o nome do canal fornecido na configuração do canal de dados para o recurso de Faturamento eletrônico no RCS).
6. No campo **Descrição**, insira uma descrição. No campo **Empresa**, selecione a entidade legal.
7. No campo **Contexto do documento**, selecione **Contexto de documento fiscal – modelo de contexto da fatura do cliente**.
8. No grupo de campos **Importar fontes**, selecione **Adicionar**.
9. No campo **Nome**, insira **XmlFile** (o nome do **Filtro de anexo** fornecido na configuração do canal de dados para o recurso de Faturamento eletrônico no RCS).
10. No campo **Descrição**, insira uma descrição e, no campo **Nome da entidade de dados**, selecione **Documentos XML da NF-e recebida**.
11. No campo **Mapeamento de modelos**, selecione **Importação de correio de NF-e – importação de correio de NF-e (BR)** e, em seguida, **Salvar**.
12. Na guia **Documento eletrônico**, no grupo de campos **Relatório Eletrônico**, selecione **Adicionar** e, no campo **Nome da tabela**, **Documento XML da NF-e recebida**.
13. No campo **Contexto do documento**, selecione **Consultar contexto de documento fiscal – contexto da fatura do cliente**.
14. No campo **Mapeamento de modelos de documento eletrônico**, selecione **Consultar mapeamento – mapeamento de documento fiscal**.
15. Selecione **Tipos de resposta** e selecione **Novo**.
16. No campo **Tipo de resposta** , insira **Resposta**. No campo **Status de envio**, insira **Agendado**.
17. No campo **Mapeamento de modelos**, selecione **Mapeamento de modelo da mensagem de resposta – formato de importação de mensagem de resposta**.
18. Selecione **Salvar** e feche a página.

### <a name="import-peppol-electronic-vendor-invoices"></a>Importar faturas eletrônicas de fornecedor PEPPOL

1. Acesse o espaço de trabalho **Relatório Eletrônico** e selecione **Configurações de relatórios**.
2. Selecione **Modelo de contexto de nota fiscal de cliente** e, em seguida, **Criar configuração** > **Derivar do Nome: Modelo de contexto de fatura de cliente, Microsoft** para criar uma configuração derivada.
3. Na versão de **Resumo**, selecione **Designer** e, na árvore **Modelo de dados**, selecione **Mapear modelo para datasource**.
4. Na árvore **Definições**, selecione **DataChannel** e, em seguida, **Designer**.
5. Na árvore **Fontes de dados**, expanda o contêiner **$Context\_Channel**. No campo **Valor**, selecione **Editar** e insira o nome do canal de dados. Este é o nome do canal fornecido na configuração do canal de dados para o recurso de Faturamento eletrônico no RCS. 
7. Selecione **Salvar** e feche a página.
8. Feche a página.
9. Selecione a configuração derivada que você acabou de criar a partir do **Modelo de contexto de fatura de cliente** e, na FastTab **Versões**, selecione **Alterar status** > **Concluído**.
10. Acesse **Administração da organização** > **Configuração** > **Parâmetros de documento eletrônico** e, na guia **Recursos**, certifique-se de que **Faturas eletrônicas globais PEPPOL** esteja selecionado. 
11. Na guia **Canais externos**, no grupo de campos **Canais**, selecione **Adicionar**.
12. No campo **Canal**, insira o nome do canal de dados e, no campo **Descrição**, insira uma descrição.
13. No campo **Empresa**, selecione a entidade legal. 
14. No campo **Contexto do documento**, selecione a nova configuração derivada do **Modelo de contexto da fatura do cliente**. A descrição do mapeamento deve ser **Contexto de canal de dados**.
15. No grupo de campos **Importar fontes**, selecione **Adicionar**.
16. No campo **Nome**, digite o **Nome do filtro de anexos** e, no campo **Nome da entidade de dados**, selecione **Cabeçalho da fatura de fornecedor**.
17. No campo **Mapeamento de modelos**, selecione **Importação de fatura de fornecedor – Importar fatura de fornecedor**.
18. Clique em **Salvar** e feche a página.


## <a name="receive-electronic-invoices"></a>Receber faturas eletrônicas

O serviço de Faturamento Eletrônico executa duas etapas durante a importação da fatura dos canais de dados:

1. Acessa a caixa de correio e lê emails.
2. Processa os emails. 
    
Para executar essas duas etapas, o cliente deve chamar o serviço manualmente para cada etapa. No entanto, recomendamos que você configure lotes para receber documentos eletrônicos.

Para receber faturas eletrônicas, siga estas etapas:

1. Acesse **Administração da organização** > **Periódico** > **Documentos eletrônicos** > **Receber documentos eletrônicos**.
2. Selecione **OK** e feche a página.


## <a name="view-receive-logs-for-electronic-invoices"></a>Exibir logs de recebimento de faturas eletrônicas

Para exibir os logs de recebimento de faturas eletrônicas, Acesse **Administração da organização** > **Periódico** > **Documentos eletrônicos** > **Log de recebimento de documentos eletrônicos**.
Se não houver faturas processadas com êxito, remova o filtro de tabela.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
