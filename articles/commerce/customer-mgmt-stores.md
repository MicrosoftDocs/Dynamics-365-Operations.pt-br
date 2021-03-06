---
title: Gerenciamento de clientes em lojas
description: Este tópico explica como os varejistas podem habilitar os recursos de gerenciamento de clientes no ponto de venda (PDV) no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 05/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd17593d84a8bf262712a84b11829f8ec6c49049
ms.sourcegitcommit: c5c8f19a696ad4a3d68dffd63bfe7b484b999d2b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6097199"
---
# <a name="customer-management-in-stores"></a>Gerenciamento de clientes em lojas

[!include [banner](includes/banner.md)]

Este tópico explica como os varejistas podem habilitar os recursos de gerenciamento de clientes no ponto de venda (PDV) no Microsoft Dynamics 365 Commerce.

É importante que os associados da loja possam criar e editar registros de clientes no PDV. Dessa forma, eles podem capturar qualquer atualização para informações do cliente, como o endereço de email, o número de telefone e o endereço. Essas informações são úteis em sistemas downstream, como marketing, pois a eficácia desses sistemas depende da precisão dos dados do cliente.

Os associados de vendas podem disparar o fluxo de trabalho de criação de clientes de dois pontos de entrada de PDV. Eles podem selecionar um botão que esteja mapeado para a operação **Adição do cliente** ou podem selecionar **Criar cliente** na barra de aplicativos na página de resultados da pesquisa. Em ambos os casos, a caixa de diálogo **Novo cliente** é exibida, na qual os associados de vendas podem inserir os detalhes necessários do cliente, como o nome do cliente, o endereço de email, o número de telefone, o endereço e as informações adicionais relevantes ao negócio. Essas informações adicionais podem ser capturadas usando os atributos do cliente associados ao cliente. Para obter mais informações sobre atributos de cliente, consulte [Atributos de cliente](dev-itpro/customer-attributes.md).

Os associados de vendas também podem capturar endereços de email e números de telefone secundários. Além disso, eles podem capturar a preferência do cliente no recebimento de informações de marketing por meio de qualquer um desses endereços de email ou números de telefone secundários. Para habilitar esse recurso, os varejistas devem ativar o recurso **Capturar vários emails e números de telefone e consentimento para marketing sobre esses contatos** no espaço de trabalho **Gerenciamento de recursos** no Commerce Headquarters (**Administração de sistemas \> Espaços de trabalho \> Gerenciamento de recursos**).

## <a name="default-customer-properties"></a>Propriedades padrão do cliente

Os varejistas podem usar a página **Todas as lojas** no Commerce Headquarters (**Varejo e Comércio \> Canais \> Lojas**) para associar um cliente padrão a cada loja. O Commerce então copia as propriedades definidas para o cliente padrão para todos os novos registros de cliente que são criados. Por exemplo, a caixa de diálogo **Criar cliente** mostra as propriedades herdadas do cliente padrão associado à loja. Essas propriedades incluem o **tipo de cliente**, **grupo de clientes**, **opção de recibo**, **e-mail de recibo**, **moeda** e **idioma**. Quaisquer **afiliações** (agrupamentos de clientes) também são herdadas do cliente padrão. Porém, as **dimensões financeiras** são herdadas do grupo de clientes associado ao cliente padrão, e não do próprio cliente padrão.

> [!NOTE]
> O **valor do email** será copiado do cliente padrão somente se a ID do email de recebimento não for fornecida para os clientes recentemente criados. Isso significa que, se a ID do email de recebimento estiver presente no cliente padrão, todos os clientes criados no site de comércio eletrônico receberão a mesma ID de email, já que não há interface do usuário para capturar a ID de email do recibo do cliente. É recomendável manter o campo **email de recibo** vazio para o cliente padrão da loja e usá-lo somente se você tiver um processo comercial que dependa de um endereço de email de recebimento presente. 

Os associados de vendas podem capturar vários endereços para um cliente. O nome e o número de telefone do cliente são herdados das informações de contato associadas a cada endereço. A Guia Rápida **Endereços** de um registro de cliente inclui um campo **Finalidade** que os associados de vendas podem editar. Se o tipo de cliente for **Pessoa**, o valor padrão será **Residência**. Se o tipo de cliente for **Organização**, o valor padrão será **Empresa**. Outros valores para os quais esse campo oferece suporte incluem: **Residência**, **Escritório** e **Caixa postal**. O valor do campo **País** para um endereço é herdado do endereço principal especificado na página **Unidade operacional** do Commerce Headquarters em **Administração da organização \> Organizações \> Unidades operacionais**.

## <a name="sync-customers-and-async-customers"></a>Sincronizar clientes e clientes assíncronos

No Commerce, há dois modos de criação de clientes: Síncrono e Assíncrono. Por padrão, os clientes são criados de forma síncrona. Em outras palavras, eles são criados no Commerce Headquarters em tempo real. O modo Síncrono de criação de clientes é benéfico porque novos clientes são pesquisados imediatamente nos canais. No entanto, ele também tem uma desvantagem. Como ele gera chamadas do [Commerce Data Exchange: Serviço em tempo real](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) para o Commerce Headquarters, o desempenho poderá ser afetado se várias chamadas simultâneas de criação de clientes forem feitas.

Se a opção **Criar cliente no modo assíncrono** estiver definida como **Sim** no perfil de funcionalidade da loja (**Varejo e Comércio \> Configuração do canal \> Configuração da loja online \> Perfis de funcionalidade**), as chamadas do Serviço em Tempo Real não são usadas para criar registros de cliente no banco de dados do canal. O modo Assíncrono de criação de clientes não afeta o desempenho do Commerce Headquarters. Um GUID (identificador global exclusivo) temporário é atribuído a cada novo registro de cliente Assíncrono e usado como a ID da conta do cliente. Esse GUID não é exibido aos usuários do PDV. Em vez disso, esses usuários verão **Sincronização pendente** como a ID da conta do cliente. Embora essa configuração force os clientes a serem criados assincronamente, observe que as edições nos registros de clientes sempre são feitas de forma síncrona.

### <a name="convert-async-customers-to-sync-customers"></a>Converter clientes Assíncronos em clientes Síncronos

Para converter clientes Assíncronos em clientes Síncronos, primeiro você deverá executar o trabalho P para enviar os clientes Assíncronos para o Commerce Headquarters. Em seguida, execute o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** para criar IDs da conta de cliente. Por fim, execute o trabalho **1010** para sincronizar as novas IDs da conta de cliente para os canais.

### <a name="async-customer-limitations"></a>Limitações do cliente Assíncrono

No momento, a funcionalidade de cliente Assíncrono tem as seguintes limitações:

- Os registros de clientes Assíncronos não podem ser editados a menos que o cliente tenha sido criado no Commerce Headquarters e a nova ID da conta do cliente tenha sido sincronizada novamente com o canal.
- As afiliações não podem ser associadas a clientes Assíncronos. Portanto, novos clientes Assíncronos não herdam as afiliações do cliente padrão.
- Os cartões-fidelidade não podem ser emitidos para clientes Assíncronos a menos que a nova ID da conta do cliente tenha sido sincronizada novamente para o canal.
- Não é possível capturar endereços de email e números de telefone secundários para clientes Assíncronos.

### <a name="customer-creation-in-pos-offline-mode"></a>Criação de cliente no modo offline do PDV

Se o PDV ficar offline enquanto o modo de criação de cliente Assíncrono estiver habilitado, novos registros de clientes serão criados assincronamente. Se o PDV ficar offline enquanto o modo de criação de cliente Assíncrono estiver desabilitado, o sistema alternará automaticamente para o modo de criação de cliente Assíncrono. Em outras palavras, os registros do cliente podem ser criados assincronamente, mesmo se o modo de criação do cliente Assíncrono estiver desabilitado. Portanto, os administradores do Commerce Headquarters devem criar e agendar um trabalho em lotes recorrente para o trabalho P, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** e o trabalho **1010**, para que todos os clientes Assíncronos sejam convertidos em clientes Síncronos no Commerce Headquarters.

> [!NOTE]
> Se a opção **Filtrar tabelas de dados do cliente compartilhadas** for definida como **Sim** na página **Esquema de canal do Commerce** (**Varejo e Comércio \> Configuração do Headquarters \> Agendador do Commerce \> Grupo de bancos de dados do canal**), os registros de cliente não serão criados no modo offline de PDV. Para obter mais informações, consulte [Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Recursos adicionais

[Atributos de clientes](dev-itpro/customer-attributes.md)

[Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
