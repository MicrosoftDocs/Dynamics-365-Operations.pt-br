---
title: Inserir dados do candidato e da solicitação de emprego manualmente
description: Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ea39e86ace40cd8e3ad2733b7f7f7a873a963e7
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693031"
---
# <a name="enter-applicant-and-application-data-manually"></a>Inserir dados do candidato e da solicitação de emprego manualmente

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego.   Você pode inserir e manter as informações pessoais, as datas e os horários de entrevista, as referências, as competências e as solicitações de acomodação para candidatos. Você também pode atualizar o status das ordens de candidatos de emprego e criar cartas ou mensagens de email para comunicar-se com os candidatos. Quando você criar um registro do candidato, um registro para o candidato é criado no catálogo de endereços global.       A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-new-applicant-record"></a>Criar um novo registro de candidato
1. Vá para Recursos humanos > Recrutamento > Candidatos > Candidatos.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Sobrenome, digite um valor.
    * Você pode inserir informações adicionais do candidato se estiver disponível. Por exemplo, as informações podem incluir o nível mais alto do candidato, o cargo atual ou o empregador anterior.  
5. Alternar a expansão da seção Informações de contato.
6. Clique em Adicionar.
7. No campo Descrição, digite 'Email de comunicação'.
8. No campo Tipo, selecione uma opção.
9. No campo Número/endereço de contato, digite um valor.
    * Este endereço de email será usado para gerar comunicação de email com o candidato.  
10. Clique em Adicionar.
11. No campo Descrição, digite um valor.
12. No campo Número/endereço de contato, digite um valor.
    * Informações pessoais do candidato.  
    * Você pode inserir as informações pessoais adicionais do candidato, se necessário. Por exemplo, isso pode incluir a data de nascimento, a origem étnica, o gênero ou o estado civil.  
13. No Painel de Ação, clique em Competências.
    * Você pode inserir o perfil de competência do candidato, incluindo suas experiências, habilidades profissionais, formação educacional, testes ou os certificados.  
    * Essas informações podem ser usadas para mapear habilidades do candidato às habilidades associadas ao trabalho definidas nos dados da empresa.   

## <a name="create-an-application-for-the-applicant"></a>Crie uma solicitação de emprego para o candidato
1. Clique em Solicitação de emprego.
2. Clique em Novo.
3. No campo Projeto de recrutamento, clique no botão suspenso para abrir a pesquisa.
    * Selecionando um projeto de recrutamento, o candidato será associado a uma determinada abertura incluída no projeto de recrutamento.  
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.
    * Por padrão, os trabalhos e o departamento são baseados no projeto de recrutamento selecionado.  
6. Clique em Salvar.
    * Após salvar a solicitação de emprego, você pode anexar documentos, inclusive a experiência do candidato, os prêmios e a carta de apresentação.  

