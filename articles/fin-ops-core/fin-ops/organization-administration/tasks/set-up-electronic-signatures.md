---
title: Configurar assinaturas eletrônicas
description: Utilize esse procedimento para configurar assinaturas eletrônicas.
author: maertenm
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4075e47013bb6a3f42cb07f88df121cef8688463cab25c4a734c5363106ace4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749523"
---
# <a name="set-up-electronic-signatures"></a>Configurar assinaturas eletrônicas

[!include [banner](../../includes/banner.md)]

Utilize esse procedimento para configurar assinaturas eletrônicas. Uma assinatura eletrônica confirma a identidade de uma pessoa que está prestes a iniciar ou aprovar um processo de computação. A empresa de dados demonstrativos utilizada para criar esse procedimento é a DAT.


## <a name="enable-the-electronic-signature-configuration-key"></a>Habilitar a chave de configuração da Assinatura eletrônica
1. Acesse Administração de sistema > Configuração > Configuração de licença.
2. Na árvore, expanda 'Administração'.
    * Verifique se a caixa de seleção Assinatura eletrônica está selecionada.  
    * Se a caixa de seleção Assinatura eletrônica não estiver selecionada, você deve habilitar o modo de manutenção. O modo de manutenção pode ser habilitado nesse ambiente através da execução de um trabalho de manutenção da Lifecycle Services, ou utilizando a ferramenta Deployment.Setup localmente.  
3. Feche a página.

## <a name="set-up-electronic-signature-parameters"></a>Configurar parâmetros de assinatura eletrônica
1. Acesse Administração da organização > Configuração > Assinatura eletrônica > Parâmetros da assinatura eletrônica.
2. Clique em Editar.
3. No campo Aviso, digite um valor.
    * Insira o aviso que os signatários receberão quando uma assinatura for exigida. Você pode inserir qualquer texto. Normalmente, esse texto informa sobre o que significa assinar um documento eletronicamente.  
    * Se você deseja inserir Texto de alerta em outros idiomas, clique no botão Traduções.  
4. Clique em Salvar.
5. Feche a página.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>Configurar códigos de motivos para assinaturas eletrônicas
1. Acesse Administração da organização > Configuração > Assinatura eletrônica > Códigos de motivo da assinatura eletrônica.
2. Clique em Novo.
    * Você deve configurar códigos de motivos antes de usar assinaturas eletrônicas. Um código de motivo válido é necessário para assinar um documento.     Um signatário seleciona um código de motivo para indicar a finalidade da assinatura eletrônica. Por exemplo, um código de motivo pode ser usado para indicar aprovação legal.  
3. No campo Código de motivo, digite um valor.
4. No campo Descrição, digite um valor.
    * Insira códigos de motivo adicionais, se necessário.  
5. Clique em Salvar.
6. Feche a página.

## <a name="require-electronic-signatures-for-existing-processes"></a>Solicitar assinaturas eletrônicas para processos existentes
1. Acesse Administração da organização > Configuração > Assinatura eletrônica > Requisitos da assinatura eletrônica.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione um processo que exija assinaturas eletrônicas.  
3. Marque ou desmarque a caixa de seleção Assinatura necessária.
    * Repita essas etapas para cada processo que exigir assinaturas eletrônicas.  
4. Clique em Salvar.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>Criar um requisito personalizado para assinaturas eletrônicas
1. Clique em Novo.
2. Marque ou desmarque a caixa de seleção Assinatura necessária.
3. No campo Nome, insira um nome para o processo que exige assinaturas eletrônicas.
4. No campo Nome da tabela, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione a tabela onde os dados que devem ser assinados estão armazenados.
6. Na lista, clique no link na linha selecionada.
7. No campo Nome do campo, clique no botão suspenso para abrir a pesquisa.
8. Na lista, localize e selecione o campo da tabela que você deseja monitorar.
9. Na lista, clique no link na linha selecionada.
    * Especifique quando uma assinatura é necessária.     Selecione Sempre se uma assinatura for necessária quando os dados do campo forem alterados.     Selecione Apenas se uma assinatura é necessária somente sob certas condições. Se você selecionar Apenas, você também deverá selecionar uma das seguintes opções: Quando um registro é inserido, Quando um registro é atualizado, ou Quando um registro é excluído.  
10. Clique em Salvar.
11. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]