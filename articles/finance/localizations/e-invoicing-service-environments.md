---
title: Ambientes de serviço
description: Este artigo fornece informações sobre os ambientes de serviço para o Faturamento eletrônico e explica como os configurar.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: ff6f50ff78676f5efed7d905fb622ad662b541d7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291589"
---
# <a name="service-environments"></a>Ambientes de serviço

[!include [banner](../includes/banner.md)]

Os ambientes de serviço são partições lógicas criadas para oferecer suporte aos recursos de Globalização e aos documentos correspondentes que são processados no Faturamento eletrônico. Os segredos de segurança e os certificados digitais, bem como as permissões de acesso (governança), devem ser configurados em nível do ambiente de serviço.

Você pode criar quantos ambientes de serviço quiser. Todos os ambientes de serviço que você cria são independentes um do outro. Como prática recomendada, crie pelo menos dois ambientes de serviço:

- Um ambiente para fins de desenvolvimento e validação principais. Esse ambiente normalmente é um ambiente de teste de aceitação de usuários (UAT).
- Um ambiente para fins de produção. Esse ambiente geralmente é um ambiente de produção.

Esse tipo de particionamento ajuda a garantir que os processos de faturamento eletrônico sejam validados e personalizados na área de armazenamento antes que eles voltem para a produção.

Os ambientes de serviço devem ser criados e mantidos no Regulatory Configuration Service (RCS). Então, quando eles estiverem prontos, deverão ser publicados no serviço de Faturamento eletrônico. O processo de publicação envia os parâmetros do ambiente de serviço da instância RCS para o serviço de faturamento eletrônico.

Se você não concluir o processo de publicação depois de criar um novo ambiente de serviço ou ajustar um ambiente de serviço existente (por exemplo, adicionando ou removendo usuários ou Microsoft Azure segredos do cofre de chaves), as alterações não serão efetivadas. Somente ambientes publicados podem ser acessados pelo Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.

## <a name="service-environment-statuses"></a>Status do ambiente de serviço

Os ambientes de serviço podem ser gerenciados por meio de seus status. Você pode exibir o status de um ambiente na página **Ambientes de serviço**. Os seguintes status estão disponíveis:

- **Não publicado** – o ambiente foi criado, mas ainda não foi publicado.
- **Publicado** – O ambiente foi publicado no complemento de Faturamento eletrônico.
- **Alterado** – os atributos de um ambiente publicado foram alterados, mas as alterações ainda não foram publicadas.

## <a name="users"></a>Usuários

Cada ambiente de serviço deve listar os usuários que podem se conectar ao Finance ou Supply Chain Management.

## <a name="applications"></a>Solicitações

Em algumas situações, outros aplicativos que não sejam Finance ou Supply Chain Management podem precisar se conectar ao serviço de faturamento eletrônico para enviar documentos eletrônicos para processamento adicional ou para recuperar informações como o status de envio de um documento. Nesses cenários, o aplicativo deve ser definido na lista de aplicativos. Dessa forma, ele terá acesso ao serviço de faturamento eletrônico. O aplicativo também deve ser registrado como um aplicativo no Azure Active Directory (Azure AD), e o ID do objeto deve ser usada para identificá-lo. 

Como a Microsoft exige um alto nível de controle de segurança sobre os aplicativos que podem se conectar ao Serviço de faturamento eletrônico, você deve contatar a Microsoft em <DGXRegulatoryservicesengineering@service.microsoft.com> e fornecer os seguintes detalhes do aplicativo:

- ID de locatário do Azure AD
- ID do ambiente do Microsoft Dynamics Lifecycle Services (LCS)
- ID de aplicativo (ID do cliente)
- ID do Objeto
- Justificação e uma descrição de alto nível do aplicativo

A Microsoft avaliará a solicitação e registrará o aplicativo no registro de segurança para garantir que ele possa operar com o faturamento eletrônico.

## <a name="number-sequences"></a>Sequências numéricas

Caso seus cenários exijam sequências numéricas (por exemplo, em nomes de arquivo), você pode usar sequências numéricas definidas para um ambiente específico, mas que podem ser usadas em Recursos de globalização ou para um Recurso de globalização específico. Após a definição de uma sequência numérica, você pode usá-la em pipelines de variáveis e de processamento. Para rastrear seu uso, na página **Sequências numéricas**, procure um valor **Atual** para o parâmetro **Em uso**.

### <a name="working-with-number-sequences"></a>Trabalhar com sequências numéricas
Na página **Sequências numéricas**: 

- Selecione **Novo** para criar uma sequência numérica. Em seguida, digite um nome e uma descrição. 
- Selecione **Excluir** para excluir uma sequência numérica, caso ela não seja mais usada.
- Não é necessário selecionar **Publicar** no Painel de ação para publicar as alterações em uma sequência numérica. A atualização é feita automaticamente.

## <a name="create-a-key-vault-reference"></a>Criar uma referência do Key Vault

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Configuração de ambiente**, no Painel de Ações, selecione **Ambientes de serviço**.
4. Na página **Ambientes de serviço**, no Painel de Ações, selecione **Parâmetros do Key Vault**.
5. Na página **Parâmetros de Key Vault**, selecione **Novo** para criar uma referência do Key Vault.
6. No campo **Nome**, insira o nome da referência do Key Vault.
7. No campo **Descrição**, insira uma descrição.
8. No campo **URI do Key Vault**, cole a URI do Key Vault do cofre de chaves (`https://<your key vault>.vault.azure.net/`). Para obter mais informações, consulte [Criar um cofre de chaves do Azure no Portal do Azure](e-invoicing-create-azure-key-vault-azure-portal.md).
9. Selecione **Salvar**.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>Criar um segredo para o token secreto da conta de armazenamento

1. Na página **Parâmetros do cofre de chaves**, selecione a referência do cofre de chaves que você criou no procedimento anterior e, em seguida, na seção **Certificados**, selecione **Adicionar**.
2. No campo **Nome**, insira o nome do segredo da conta de armazenamento. Esse nome deve corresponder ao nome do segredo do Key Vault que contém o token de assinatura de acesso compartilhado (SAS) de armazenamento. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure no Portal do Azure](e-invoicing-create-azure-storage-account-azure-portal.md). 
3. No campo **Descrição**, insira uma descrição.
4. No campo **Tipo**, selecione **Segredo**.
5. Selecione **Salvar**.
    
## <a name="create-a-service-environment"></a>Criar um ambiente de serviço

1. Na página **Ambientes de serviço**, no Painel de Ações, selecione **Novo** para criar um ambiente de serviço.
2. No campo **Nome**, insira o nome do ambiente de Faturamento eletrônico.
3. No campo **Descrição**, insira uma descrição.
4. No campo **Segredo de token SAS de armazenamento**, selecione o nome do segredo da conta de armazenamento que deve ser usado para autenticar o acesso à conta de armazenamento.
5. Na seção **Usuários**, selecione **Adicionar** para adicionar um usuário que tem permissão para enviar faturas eletrônicas pelo ambiente e para se conectar à conta de armazenamento.
6. No campo **ID do Usuário**, insira o alias do usuário. 
7. No campo **Email**, insira o endereço de email do usuário.
8. Selecione **Salvar**.
9. No Painel de Ações, selecione **Publicar** para publicar o ambiente no serviço de Faturamento eletrônico. Verifique se o valor do campo **Status** foi alterado para **Publicado**.
