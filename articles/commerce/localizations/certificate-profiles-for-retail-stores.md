---
title: Perfis de certificado definidos pelo usuário para lojas de varejo
description: Este artigo fornece uma visão geral dos perfis de certificado disponíveis no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: v-chgriffin
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: 5baf043a43210d819b605546089e981c86922ca9
ms.sourcegitcommit: 4f28f262cfb8f047cb5c0070261aa0748835e74b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2022
ms.locfileid: "9558428"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Perfis de certificado definidos pelo usuário para lojas de varejo

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral dos perfis de certificado disponíveis no Microsoft Dynamics 365 Commerce. Essa funcionalidade estende o recurso [Gerenciar segredos para canais de varejo](../dev-itpro/manage-secrets.md) adicionando suporte a certificados locais.

Enquanto o ponto de venda (PDV) estiver sendo executado no modo offline, ele não poderá acessar os certificados armazenados no Microsoft Azure Key Vault. Em vez disso, o certificado local deve ser usado. Os seguintes recursos têm suporte:

- Usando certificados locais em cenários de fallback do Key Vault
- Usando certificados locais sem o Key Vault (por exemplo, em uma instalação local)
- Atualização gradual de certificados, em que algumas lojas e terminais usam uma nova versão do certificado, mas outras lojas e terminais continuam a usar a versão anterior

A funcionalidade de perfis de certificado permite especificar um certificado padrão e definir a ordem em que os certificados no mesmo perfil de certificado são pesquisados. Essa funcionalidade também fornece uma abordagem de configuração semelhante para certificados locais e certificados do Key Vault. Você pode adicionar configurações específicas da empresa para certificados, mas o identificador exclusivo entre empresas para cada certificado pode ser usado nos canais do Commerce.

### <a name="scenarios"></a>Cenários

A funcionalidade de perfis de certificado oferece suporte aos seguintes cenários nos canais do Commerce:

- Use um certificado local em cenários de fallback do Key Vault. Veja aqui alguns exemplos desses cenários de fallback:

    - O armazenamento do cofre de chaves não está acessível.
    - Um certificado não foi encontrado no armazenamento do cofre de chaves.
    - O PDV está sendo executado no modo offline.

- Use certificados locais, mas sem armazená-los no Key Vault (por exemplo, em uma instalação local).
- Faça uma atualização gradual de certificados, em que uma nova versão do certificado é usada somente em lojas ou em terminais em que a nova versão já está disponível.
- Use o mesmo certificado em várias empresas.

## <a name="set-up-certificate-profiles"></a>Configurar perfis de certificado

O procedimento a seguir explica como configurar perfis de certificado.

### <a name="set-up-key-vault"></a>Configurar o Key Vault

As etapas a seguir devem ser concluídas antes que você possa usar um certificado digital armazenado no Key Vault.

1. Crie uma conta de armazenamento do Key Vault. Recomendamos implantar a conta de armazenamento na mesma região geográfica que a Commerce Scale Unit.
1. Carregue o certificado digital na conta de armazenamento do Key Vault.
1. Autorize o aplicativo AOS (Servidor de Objetos de Aplicativo) a ler segredos da conta de armazenamento do Key Vault.

Para obter mais informações sobre como trabalhar com o Key Vault, consulte [Introdução do Azure Key Vault](/azure/key-vault/key-vault-get-started).

### <a name="set-up-system-parameters"></a>Configurar os parâmetros do sistema

Antes de configurar perfis de certificado nos canais do Commerce, você deve habilitar o Commerce para usar os dois certificados armazenados no Key Vault e nos perfis de certificado.

Para configurar parâmetros do sistema no Commerce headquarters, siga estas etapas:

1. Na página **Parâmetros do sistema**, defina a opção **Usar repositório de certificados avançado** como **Sim**.
1. No espaço de trabalho **Gerenciamento de recursos** , ative o recurso **Perfis de certificado definidos pelo usuário para lojas de varejo**.

### <a name="set-up-key-vault-parameters"></a>Configurar parâmetros do Key Vault

Na página **Parâmetros do Key Vault**, você deve especificar os seguintes parâmetros para acessar o armazenamento do Key Vault:

- **Nome** e **Descrição** – o nome e a descrição da conta de armazenamento do Key Vault.
- **URL do Key Vault** – a URL da conte de armazenamento do Key Vault.
- **Cliente do Key Vault** – uma ID do cliente interativa do aplicativo Azure Active Directory (Azure AD) associado à conta de armazenamento do Key Vault para fins de autenticação. Esse cliente deve ter acesso para ler segredos da conta de armazenamento.
- **Chave secreta do Key Vault** – uma chave secreta associada ao aplicativo do Azure AD usado para autenticação na conta de armazenamento do Key Vault.
- **Nome**, **Descrição** e **Referência secreta** – O nome, a descrição e a referência secreta do certificado.

Para obter mais informações, consulte [Configurar o cliente do Azure Key Vault](../../finance/localizations/setting-up-azure-key-vault-client.md).

### <a name="configure-a-certificate-profile"></a>Configurar um perfil de certificado

Para configurar um perfil de certificado no Commerce headquarters, siga estas etapas:

1. Acesse **Administração do sistema \> Configurar \> Perfis de certificado**.
1. No Painel de Ação, selecione **Novo** para criar um registro.
1. Insira os valores nos campos **Perfil de certificado**, **Nome** e **Descrição**.

    > [!NOTE]
    > O perfil de certificado é um identificador exclusivo de um certificado em todas as empresas e componentes do Commerce.

1. Na Guia Rápida **Entidades legais**, selecione **Adicionar** para adicionar uma linha.
1. Em **Entidade legal**, selecione a entidade legal (empresa) para a qual o perfil de certificado atual deve ser usado.

    Se o perfil de certificado tiver que ser usado para várias entidades legais, repita as etapas 4 e 5 para adicionar uma linha para cada entidade legal adicional.

1. Selecione **Configurações** para abrir a página **Configurações do perfil de certificado**, na qual você pode inserir configurações específicas da empresa para o perfil de certificado. Especifique quais certificados podem ser usados quando o perfil atual do certificado é chamado nos canais do Commerce. Adicione quantos certificados forem necessários e defina prioridades para eles. Se um certificado com prioridade mais alta não estiver disponível, o próximo certificado será usado, com base na prioridade. Para obter mais informações, consulte a seção [Fluxo de trabalho: pesquisando certificados no Commerce Runtime](#workflow-searching-certificates-in-the-commerce-runtime).

    > [!NOTE]
    > O campo **Prioridade** é definido automaticamente. O valor **1** representa a prioridade mais alta. Quando uma nova linha é adicionada na página **Configurações do perfil de certificado**, sua prioridade é definida como um número maior do que a prioridade da linha anterior. Para alterar a prioridade de uma linha específica, selecione a linha e selecione **Mover para cima** para aumentar a prioridade ou **Mover para baixo** para diminuir a prioridade.

1. Ao adicionar uma nova linha na página **Configurações do perfil de certificado**, defina os seguintes campos:

    - **Tipo de local** – selecione o local onde o certificado está armazenado. Esse campo tem dois valores possíveis: **Certificado local** e **Key Vault**.
    - **Certificado do Key Vault** – esse campo será obrigatório se você definir o campo **Tipo de local** como o **Key Vault**. Use-o para especificar um segredo de certificado do Key Vault.
    - **Nome da loja** – esse campo é opcional e só estará disponível se você definir o campo **Tipo de local** como **Certificado local**. Use-o para especificar um nome de armazenamento padrão que deve ser usado para pesquisar certificados locais.
    - **Local da loja** – esse campo é opcional e só estará disponível se você definir o campo **Tipo de local** como **Certificado local**. Use-o para especificar um local de armazenamento padrão que deve ser usado para pesquisar certificados locais.

        > [!NOTE]
        > O nome da loja e o local da loja padrão são adicionados para simplificar o processo de pesquisa de certificados locais no Commerce Runtime. X509StoreProvider tem uma lista de pastas em que os certificados estão armazenados. Se o nome do armazenamento padrão e o local de armazenamento padrão não forem especificados, o X509StoreProvider tentará encontrar um certificado nas outras pastas na lista. Para obter mais informações sobre os valores disponíveis para o nome do armazenamento e o local de armazenamento, consulte [Enumeração de StoreName](/dotnet/api/system.security.cryptography.x509certificates.storename) e [Enumeração de StoreLocation](//dotnet/api/system.security.cryptography.x509certificates.storelocation).

    - **Impressão digital** – esse campo é obrigatório e só estará disponível se você definir o campo **Tipo de local** como **Certificado local**. Use-o para especificar a impressão digital do certificado.

        > [!IMPORTANT]
        > Você deve garantir que o usuário que executa o aplicativo que tem de usar o certificado local (por exemplo, o Modern POS no modo offline) tenha, pelo menos, acesso somente leitura à chave privada do certificado.

    - **Comentários** – esse campo é opcional e permite que os usuários insiram anotações.

## <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Fluxo de trabalho: pesquisa de certificados no Commerce Runtime

Este é o fluxo de trabalho básico usado para pesquisar um certificado quando um perfil de certificado é chamado no Commerce Runtime.

1. O sistema identifica se o perfil do certificado tem configurações específicas da empresa para a entidade legal atual.
1. O sistema tenta localizar o certificado usando os valores na página **Configurações do perfil de certificado** para a linha em que o campo **Prioridade** está definido como **1**.

    - Se o campo **Tipo de local** for definido como **Key Vault**, o valor do campo **Segredo do certificado do Key Vault** será usado para procurar o certificado na página **Parâmetros do cofre de chaves**. Em seguida, o certificado é procurado no armazenamento do cofre de chaves.
    - Se o campo **Tipo de local** estiver definido como **Certificado local**, o X509StoreProvider primeiro procurará o certificado usando o nome de armazenamento padrão e o local de armazenamento, se esses parâmetros forem especificados. Em seguida, ele pesquisará todas as outras pastas na lista de pastas.

1. Se o certificado não for encontrado, o processo será repetido para a linha em que o campo **Prioridade** está definido como **2**, e assim por diante.

> [!NOTE]
> Se o perfil do certificado não tiver configurações para a entidade legal atual ou se a pesquisa do certificado não for bem-sucedida para todas as linhas na página **Configurações do perfil de certificado** , o certificado não será encontrado.

### <a name="caching-the-results-of-certificate-searches"></a>Como armazenar em cache os resultados de pesquisas de certificados

Os resultados de pesquisas de certificados são armazenados em cache. O período de expiração padrão de um cache é de uma hora. No entanto, esse tempo pode ser personalizado e pode ser definido para um valor máximo de 24 horas.

## <a name="gradual-update"></a>Atualização gradual

Se uma nova versão do certificado for introduzida, mas não puder ser atualizada em todas as lojas ao mesmo tempo, a funcionalidade de perfis de certificado permitirá que o certificado seja atualizado gradualmente.

1. Localize um perfil de certificado e a linha que deve ser atualizada e, em seguida, selecione **Configurações**.
1. Adicione uma linha e especifique as configurações relacionadas à versão mais recente do certificado.
1. Aumente o valor de **Prioridade** da nova linha. Use o botão **Mover para cima** para mover a linha de forma que ela fique acima da linha da versão anterior do mesmo certificado.
> [!NOTE]
> No Commerce Runtime, a nova versão do certificado será chamada primeiro. Se o certificado ainda não tiver sido atualizado em uma loja específica ou em um terminal específico, a versão anterior será chamada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
