---
title: Perfis de certificado definidos pelo usuário para lojas de varejo
description: Este artigo fornece uma visão geral sobre como os certificados são usados em lojas de varejo.
author: josaw
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1b40c74efa56a6e18af907e000554b9ab269bb31
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873020"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Perfis de certificado definidos pelo usuário para lojas de varejo

[!include [banner](../includes/banner.md)]


## <a name="overview"></a>Visão geral

Este artigo fornece uma visão geral dos perfis de certificado disponíveis no Microsoft Dynamics 365 Commerce. Essa funcionalidade estende o recurso [Gerenciar segredos para canais de varejo](../dev-itpro/manage-secrets.md) adicionando suporte a certificados locais.

Enquanto o ponto de venda (PDV) estiver sendo executado no modo offline, ele não poderá acessar os certificados armazenados no cofre de chaves. Em vez disso, o certificado local deve ser usado. Os seguintes recursos têm suporte:

- Como usar certificados locais em cenários de fallback do cofre de chaves
- Como usar certificados locais sem um cofre de chaves (por exemplo, em uma instalação local)
- Atualização gradual de certificados, em que algumas lojas e terminais usam uma nova versão do certificado, mas outras lojas e terminais continuam a usar a versão anterior

A funcionalidade de perfis de certificado permite especificar um certificado padrão e definir a ordem em que os certificados no mesmo perfil de certificado são pesquisados. Essa funcionalidade também fornece uma abordagem de configuração semelhante para certificados locais e certificados do Key Vault. Você pode adicionar configurações específicas da empresa para certificados, mas o identificador exclusivo entre empresas para cada certificado pode ser usado nos canais do Commerce.

### <a name="scenarios"></a>Cenários

A funcionalidade de perfis de certificado oferece suporte aos seguintes cenários nos canais do Commerce:

- Use um certificado local em cenários de fallback do cofre de chaves. Veja aqui alguns exemplos desses cenários de fallback:

    - O armazenamento do cofre de chaves não está acessível.
    - Um certificado não foi encontrado no armazenamento do cofre de chaves.
    - O PDV está sendo executado no modo offline.

- Use certificados locais, mas sem armazená-los no cofre de chaves (por exemplo, em uma instalação na infraestrutura local).
- Faça uma atualização gradual de certificados, em que uma nova versão do certificado é usada somente em lojas ou em terminais em que a nova versão já está disponível.
- Use o mesmo certificado em várias empresas.

## <a name="set-up-certificate-profiles"></a>Configurar perfis de certificado

O procedimento a seguir explica como configurar perfis de certificado. Antes de usar perfis de certificado nos canais do Commerce, siga estas etapas para definir as configurações.

1. No espaço de trabalho **Gerenciamento de recursos** , ative o recurso **Perfis de certificado definidos pelo usuário para lojas de varejo**.
2. Acesse **Administração do sistema \> Configurar \> Perfis de certificado**.
3. Crie um registro e defina os campos **Perfil de certificado**, **Nome** e **Descrição** para ele.

    > [!NOTE]
    > O perfil de certificado é um identificador exclusivo de um certificado em todas as empresas e componentes do Commerce.

3. Na guia **Entidades legais**, adicione uma linha e selecione a entidade legal (empresa) para a qual o perfil de certificado atual deve ser usado. Se o perfil de certificado tiver de ser usado para várias entidades legais, repita essa etapa para adicionar uma linha para cada entidade legal adicional.
4. Selecione **Configurações** para abrir a página **Configurações do perfil de certificado**, na qual você pode inserir configurações específicas da empresa para o perfil de certificado.

### <a name="certificate-profile-settings"></a>Configurações de perfil de certificado

Quando você seleciona **Configurações** para linhas de perfil de certificado, a página **Configurações de perfil de certificado** é exibida. Esta página permite que você especifique quais certificados podem ser usados quando o perfil atual do certificado é chamado nos canais do Commerce. Você também pode especificar a ordem em que os certificados devem ser pesquisados.

> [!NOTE]
> O campo **Prioridade** é definido automaticamente. O valor **1** representa a prioridade mais alta. Quando uma nova linha é adicionada na página **Configurações do perfil de certificado**, sua prioridade é definida como um número maior do que a prioridade da linha anterior. Para alterar a prioridade de uma linha específica, selecione a linha e selecione **Mover para cima** para aumentar a prioridade ou **Mover para baixo** para diminuir a prioridade.

Ao adicionar uma nova linha à página **Configurações do perfil de certificado**, defina os seguintes campos:

- **Tipo de local** – selecione o local onde o certificado está armazenado. Esse campo tem dois valores possíveis: **Certificado local** e **Key Vault**.
- **Certificado do Key Vault** – esse campo será obrigatório se você definir o campo **Tipo de local** como o **Key Vault**. Use-o para especificar um segredo de certificado do Key Vault.

    > [!NOTE]
    > Antes de usar um certificado do cofre de chaves nos perfis de certificado, certifique-se de carregar um certificado para o armazenamento do cofre de chaves e siga as instruções em [Configurar o cliente do Azure Key Vault](../../finance/localizations/setting-up-azure-key-vault-client.md).

- **Nome da loja** – esse campo é opcional e só estará disponível se você definir o campo **Tipo de local** como **Certificado local**. Use-o para especificar um nome de armazenamento padrão que deve ser usado para pesquisar certificados locais.
- **Local da loja** – esse campo é opcional e só estará disponível se você definir o campo **Tipo de local** como **Certificado local**. Use-o para especificar um local de armazenamento padrão que deve ser usado para pesquisar certificados locais.

    > [!NOTE]
    > O nome da loja e o local da loja padrão são adicionados para simplificar o processo de pesquisa de certificados locais no Commerce Runtime. X509StoreProvider tem uma lista de pastas em que os certificados estão armazenados. Se o nome do armazenamento padrão e o local de armazenamento padrão não forem especificados, o X509StoreProvider tentará encontrar um certificado nas outras pastas da lista.

- **Impressão digital** – esse campo é obrigatório e só estará disponível se você definir o campo **Tipo de local** como **Certificado local**. Use-o para especificar a impressão digital do certificado.
- **Comentários** – esse campo é opcional e permite que os usuários insiram anotações.

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Fluxo de trabalho: pesquisa de certificados no Commerce Runtime

Este é o fluxo de trabalho básico usado para pesquisar um certificado quando um perfil de certificado é chamado no Commerce Runtime.

1. O sistema identifica se o perfil do certificado tem configurações específicas da empresa para a entidade legal atual.
1. O sistema tenta localizar o certificado usando os valores na página **Configurações do perfil de certificado** para a linha em que o campo **Prioridade** está definido como **1**.

    - Se o campo **Tipo de local** for definido como **Key Vault**, o valor do campo **Segredo do certificado do Key Vault** será usado para procurar o certificado na página **Parâmetros do cofre de chaves**. Em seguida, o certificado é procurado no armazenamento do cofre de chaves.
    - Se o campo **Tipo de local** estiver definido como **Certificado local**, o X509StoreProvider primeiro procurará o certificado usando o nome de armazenamento padrão e o local de armazenamento, se esses parâmetros forem especificados. Em seguida, ele pesquisará todas as outras pastas na lista de pastas.

1. Se o certificado não for encontrado, o processo será repetido para a linha em que o campo **Prioridade** está definido como **2**, e assim por diante.

> [!NOTE]
> Se o perfil do certificado não tiver configurações para a entidade legal atual ou se a pesquisa do certificado não for bem-sucedida para todas as linhas na página **Configurações do perfil de certificado** , o certificado não será encontrado.

#### <a name="caching-the-results-of-certificate-searches"></a>Como armazenar em cache os resultados de pesquisas de certificados

Os resultados de pesquisas de certificados são armazenados em cache. O período de expiração padrão de um cache é de uma hora. No entanto, esse tempo pode ser personalizado e pode ser definido para um valor máximo de 24 horas.

### <a name="gradual-update"></a>Atualização gradual

Se uma nova versão do certificado for introduzida, mas não puder ser atualizada em todas as lojas ao mesmo tempo, a funcionalidade de perfis de certificado permitirá que o certificado seja atualizado gradualmente.

1. Localize um perfil de certificado e a linha que deve ser atualizada e, em seguida, selecione **Configurações**.
1. Adicione uma linha e especifique as configurações relacionadas à versão mais recente do certificado.
1. Aumente o valor de **Prioridade** da nova linha. Use o botão **Mover para cima** para mover a linha de forma que ela fique acima da linha da versão anterior do mesmo certificado.

> [!NOTE]
> No Commerce Runtime, a nova versão do certificado será chamada primeiro. Se o certificado ainda não tiver sido atualizado em uma loja específica ou em um terminal específico, a versão anterior será chamada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]