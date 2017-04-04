---
title: "Aplicativos de PDV e configurações do idioma do usuário"
description: "Este tópico descreve como alterar as configurações do idioma no POS moderno POS (MPOS) e nublar-se POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf5b75572529bb497d3079752de187f30aa59294
ms.lasthandoff: 03/31/2017


---

# <a name="pos-application-and-user-language-settings"></a>Aplicativos de PDV e configurações do idioma do usuário

Este tópico descreve como alterar as configurações do idioma no POS moderno POS (MPOS) e nublar-se POS.

<a name="overview"></a>Visão Geral
========

POS moderno varejo (e) MPOS de pos do nuvem ambientes de suporte que as configurações e traduções de idioma podem variar entre armazenamento e as configurações do usuário. Por exemplo, o repositório ficado pode ser localizado em uma região onde o inglês embora a mais comuns de seus clientes, mas alguns trabalhadores preferem usar o aplicativo com traduções francesas.

## <a name="data-language"></a>Idioma dos dados
Independentemente das configurações do usuário, MPOS e o retail do nuvem usarão sempre configurações de idioma de determinar as traduções usadas de dados. Isso assegurar-se-á de todos os usuários e clientes tenham uma experiência consistente.  Exemplos de dados inclui:

-   Produtos
-   Atributos e valores
-   Nomes de categoria
-   Recibos de transação enviados por email ou impressos
-   Nomes de método de pagamento
-   Mensagens de exibição de linha

O idioma de armazenamento também será usado para a tela logon principal de POS, como o usuário não é conhecido antes de fazer logon. Se uma transação não estará disponível para o idioma da loja, o POS reverterá o idioma da empresa.

### <a name="configuring-the-stores-language-setting"></a>Definindo a configuração do idioma da loja

A configuração de idioma de armazenamento está definida ** de todas as lojas no chão ** ** ** pagina abaixo ** o idioma &gt; regional configurações gerais &gt; . ** Use ao consumidor para baixo para escolher o idioma para cada armazenamento.

## <a name="user-interface-language"></a>Idioma da interface do usuário
A configuração de idioma de usuário do retail determina as traduções usadas na interface de usuário do aplicativo. Isso inclui os rótulos, menus, e listas que não são consideradas dados. A exceção é texto exibido em grades de botões POS. As grades de botões não oferecem suporte traduções portanto, sempre mostrará o texto como definido no botão. Para dar suporte traduziu botões, você terá de copiar e manter separadas grades de botões e atribuí-las usuários conforme apropriado.

### <a name="configuring-the-users-language-setting"></a>Definindo a configuração do idioma do usuário

A configuração de idioma do usuário do retail pos é definida ** de todos os funcionários ** ** trabalhador ** o página abaixo ** idioma &gt; varejista **.  Não é definido na guia do perfil.  Essa configuração não é usada pelo retail. Se o idioma do usuário não for definido ou for definido como um idioma no qual as traduções não estão disponíveis, o PDV será revertido para o idioma da loja.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | ** Idioma da interface de usuário ** ** **      | **Idioma dos dados (produtos, formatos de recibo, exibição de linha etc.)** |
| **Empresa** | Padrão                    | Padrão                                                           |
| **Loja**   | Substitui a empresa          | Substitui a empresa                                                 |
| **User**    | Substitui a loja ou a empresa | Nunca                                                             |




