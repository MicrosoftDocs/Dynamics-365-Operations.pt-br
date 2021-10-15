---
title: Personalizar e usar o portal do cliente
description: Este tópico explica como personalizar o portal do cliente após ele ser adicionado ao sistema.
author: Henrikan
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 548a81d8145d6762508163f17ca7367cb5ecd849
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579007"
---
# <a name="customize-and-use-the-customer-portal"></a>Personalizar e usar o portal do cliente

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve as diferentes páginas que estão disponíveis no portal do cliente prontas para uso. Ele explica o que as páginas fazem e como você pode personalizá-las.

O portal do cliente oferece algumas páginas da Web e ações prontas para uso. O mapa do site a seguir fornece uma visão geral dessas páginas e ações, bem como as funções que podem executar as ações.

![Mapa do site de portal do cliente.](media/customer-portal-site-map.png "Mapa do site de portal do cliente")

## <a name="typical-customizations"></a>Personalizações típicas

Os tópicos a seguir ajudarão você a aprender as noções básicas sobre os portais do Power Apps e como você pode personalizar portais:

- [Trabalhar com modelos](/powerapps/maker/portals/work-with-templates) – Este tópico fornece uma visão geral de como os portais do Power Apps funcionam e como você pode fazer personalizações simples de portais.
- [Gerenciar conteúdo do portal](/dynamics365/portals/manage-portal-content) – Este tópico explica como é possível gerenciar e personalizar o conteúdo que você pode destacar no seu portal.
- [Editar CSS](/powerapps/maker/portals/edit-css) – Este tópico ajuda você a criar personalizações mais complexas na interface do usuário do seu portal.
- [Crie um tema para o seu portal](/dynamics365/portals/create-theme) – Este tópico ajuda a criar um tema da interface do usuário para o seu portal.
- [Criar e expor conteúdo do portal facilmente](/dynamics365/portals/create-expose-portal-content) – Este tópico ajuda a gerenciar os dados e as tabelas subjacentes que você usa no seu portal.
- [Configurar um contato para usar em um portal](/powerapps/maker/portals/configure/configure-contacts) – Este tópico explica como criar e personalizar funções de usuário e como a segurança e a autenticação funcionam nos portais do Power Apps.
- [Configurar notas para formulários de tabela e formulários da Web em portais](/powerapps/maker/portals/configure-notes) – Este tópico explica como adicionar documentos e armazenamento adicional ao seu portal.
- [Tratamento de erros para o site do portal](/powerapps/maker/portals/admin/view-portal-error-log) – Este tópico explica como exibir logs de erros do portal e armazená-los na sua conta de armazenamento de Blob do Microsoft Azure.

## <a name="customize-the-order-creation-process"></a>Personalizar o processo de criação de ordens

Quando um usuário envia uma ordem usando o portal do cliente, a ordem é sincronizada automaticamente com o ambiente correspondente do Dynamics 365 Supply Chain Management. Como o usuário é um cliente externo, algumas informações necessárias são intencionalmente ocultas. Essas informações serão preenchidas automaticamente quando o formulário for enviado.

Esta seção mostra como você deve configurar os contatos para evitar erros. Ele explica os campos que são definidos automaticamente e como você pode modificar o valor desses campos, se necessário.

### <a name="the-out-of-box-order-creation-process"></a>O processo de criação de ordens pronto para uso

Estas são as etapas padrão para enviar uma ordem do portal do cliente.

1. Na home page, selecione o bloco **Criar ordem** para abrir o assistente **Criar Ordem**.
1. Na página **Informações da Ordem**, defina os seguintes campos:

    - **Data de recebimento solicitada** – especifique a data de entrega.
    - **Endereço de entrega** – insira o endereço para o qual a ordem deve ser entregue.
    - **Empresa** – selecione o nome da empresa do cliente. Este campo é automaticamente definido para usuários não administradores.
    - **Número da requisição** – insira o número da requisição da ordem. Este campo não é obrigatório.
    - **Remeter para país/região** – insira o país ou a região para o qual os itens serão entregues. Este campo é automaticamente definido para usuários não administradores.

    ![Página Informações da ordem.](media/customer-portal-order-information.png "Página Informações da ordem")

1. Selecione **Avançar**.
1. Na página **Itens**, selecione **Adicionar Item**.

    ![Página Itens.](media/customer-portal-items.png "Página Itens")

1. Na caixa de diálogo **Informações de Item**, defina os seguintes campos:

    - **Nome do Produto** – localize e selecione um produto para adicionar à ordem.
    - **Quantidade** – insira a quantidade do produto selecionado.
    - **Unidade** – especifique a unidade de medida (por exemplo, **un.**, **kg** ou **caixa**).
    - **Valor líquido previsto** – o valor é calculado como o preço previsto do item × a quantidade da unidade selecionada.

    ![Caixa de diálogo Informações do Item.](media/customer-portal-item-information.png "Caixa de diálogo Informações do Item")

1. Selecione **Enviar** para adicionar o item à ordem.
1. Repita as etapas 4 a 6 até adicionar todos os itens que deseja solicitar.
1. Quando terminar de adicionar itens, selecione **Avançar** na página **Itens**.
1. A página **Informações da Ordem** fornece um resumo da ordem. Examine o conteúdo da ordem e detalhes da entrega. Se tudo parecer correto, selecione **Enviar** para enviar a ordem.

    ![Página Informações da ordem concluída.](media/customer-portal-order-submit.png "Página Informações da ordem concluída")

### <a name="standard-data-setup"></a>Configuração de dados padrão

Para ajudar a garantir uma experiência de usuário tranquila, o portal do cliente preenche automaticamente os valores para vários campos obrigatórios. Esses valores se baseiam em informações no registro de contato do cliente que está enviando a ordem.

Para cada [linha de contato](/powerapps/maker/portals/configure/configure-contacts) que pertença a um cliente que usará o portal do cliente para enviar ordens, os valores deverão ser especificados para os campos obrigatórios a seguir. Caso contrário, ocorrerão erros.

- **Empresa** – a entidade legal à qual a ordem pertence
- **Cliente em potencial** – a conta de cliente que é associada à ordem
- **Lista de preços** – a lista de preços personalizada do cliente
- **Moeda** – a moeda do preço
- **Remeter para país/região** – o país ou a região para o qual os itens serão entregues

Os seguintes campos são automaticamente definidos para a tabela da ordem de venda:

- **Idioma** – o idioma da ordem (por padrão, o valor é obtido do registro de contato).
- **Remeter para país/região** – o país ou a região para o qual os itens serão entregues (por padrão, o valor é obtido do registro de contato).
- **Pessoa de contato** – o usuário que pode ser contatado para obter informações sobre a ordem (por padrão, o valor é obtido do registro de contato).
- **Empresa** – a entidade legal à qual a ordem pertence (por padrão, o valor é obtido do registro de contato).
- **Cliente potencial** – a conta do cliente associada à ordem (por padrão, o valor é obtido do registro de contato.)
- **Cliente da fatura** – a conta de cobrança da ordem (o valor padrão é o cliente potencial do registro de contato.)
- **Nome da ordem de venda** – o nome da ordem de venda (o valor padrão é **ordem de venda**).
- **Moeda** – a moeda do preço (por padrão, o valor é obtido do registro de contato).
- **Lista de preços** – a lista de preços personalizada do cliente (por padrão, o valor é obtido do registro de contato).
- **Descrição do endereço de entrega** – o endereço de entrega da ordem de venda (o valor padrão é **descrição do endereço de entrega** .)

### <a name="modify-the-order-creation-process"></a>Modificar o processo de criação de ordens

Você poderá modificar livremente a aparência e a interface do usuário do portal do cliente se não alterar o processo básico de criação de ordem. Se desejar alterar o processo de criação de ordem, há alguns pontos a serem lembrados.

Não remova as seguintes colunas da tabela da ordem de venda no Microsoft Dataverse, pois eles são necessários para criar uma ordem de venda na gravação dupla:

- **Empresa** – a entidade legal à qual a ordem pertence
- **Nome** – o nome da ordem de venda
- **Moeda** – a moeda do preço
- **Lista de preços** – a lista de preços personalizada do cliente
- **Remeter para país/região** – o país ou a região para o qual os itens serão entregues
- **Cliente em potencial** – a conta de cliente que é associada à ordem
- **Idioma** – o idioma da ordem (normalmente, esse idioma é o idioma do cliente potencial).
- **Descrição do endereço de entrega** – o endereço de entrega da ordem de venda

Para itens, as seguintes colunas são obrigatórias:

- **Produto** – o produto a ser encomendado
- **Quantidade** – a quantidade do produto selecionado
- **Unidade** – a unidade de medida (por exemplo, **un.**, **kg** ou **caixa**)
- **Remeter para país/região** – o país ou a região de entrega
- **Descrição do endereço de entrega** – o endereço de entrega da ordem

Você deve verificar se o portal do cliente envia valores para todas essas colunas.

Se desejar adicionar ou remover colunas da página, consulte [Criar ou editar formulários de criação rápida para uma experiência de entrada de dados simplificada](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).

Se desejar alterar a forma como as colunas são predefinidas e como os valores são definidos quando a página é salva, consulte as seguintes informações na documentação dos portais do Power Apps:

- [Preencher previamente campo](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [Definir valor ao salvar](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>Personalizar a home page

Todos os controles no portal do cliente são controles internos de portais do Power Apps. Você pode personalizá-los seguindo as etapas em [Compor uma página](/powerapps/maker/portals/compose-page) na documentação de portais do Power Apps.

O único controle personalizado incluído no modelo do portal do cliente é usado para criar os blocos na home page.

![Blocos na página inicial.](media/customer-portal-home-page-tiles.png "Blocos na home page")

Para modificar os blocos, siga estas etapas.

1. Abra o [aplicativo de gerenciamento de portal](/powerapps/maker/portals/configure/configure-portal).
1. No painel de navegação à esquerda, selecione **Modelos de Página**.

    ![Painel de navegação do gerenciamento de portal.](media/customer-portal-nav.png "Painel de navegação do gerenciamento de portal")

1. Selecione o modelo de página denominado **Início**.
1. No campo **Modelo da Web**, selecione o link **Início** para abrir o código-fonte dessa página.

    ![Campo Modelo da Web.](media/customer-portal-web-template.png "Campo Modelo da Web")

1. Agora, você deve ver todo o código-fonte da home page e pode modificá-lo conforme necessário.

## <a name="resources"></a>Recursos

Para saber mais sobre como você pode configurar e personalizar o portal do cliente, consulte os seguintes recursos:

- [Documentação de portais do Power Apps](/powerapps/maker/portals/overview)
- [Documentação da gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [Sobre o ciclo de vida do portal](/powerapps/maker/portals/admin/portal-lifecycle)
- [Atualizar um portal](/powerapps/maker/portals/admin/upgrade-portal)
- [Migrar configuração do portal](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Gerenciamento do ciclo de vida da solução: Dynamics 365 para aplicativos do Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]