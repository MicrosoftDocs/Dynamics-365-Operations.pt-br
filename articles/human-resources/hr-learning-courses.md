---
title: Configurar cursos de treinamento
description: Os administradores e gerentes de recursos humanos podem usar os recursos dos cursos para manter informações sobre o treinamento que é oferecido aos funcionários.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c3c23ab6fca3f97fbca9edfe83c656e7ca8a2800
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008081"
---
# <a name="set-up-training-courses"></a><span data-ttu-id="73677-103">Configurar cursos de treinamento</span><span class="sxs-lookup"><span data-stu-id="73677-103">Set up training courses</span></span>

<span data-ttu-id="73677-104">Os administradores e gerentes de recursos humanos podem usar os recursos dos cursos para manter informações sobre o treinamento que é oferecido aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="73677-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="73677-105">Pré-requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="73677-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="73677-106">As informações a seguir são necessárias e devem ser configuradas antes de criar cursos.</span><span class="sxs-lookup"><span data-stu-id="73677-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="73677-107">**Tipos de cursos**</span><span class="sxs-lookup"><span data-stu-id="73677-107">**Course types**</span></span>

<span data-ttu-id="73677-108">As informações a seguir são informações opcionais que você poderá especificar para cursos.</span><span class="sxs-lookup"><span data-stu-id="73677-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="73677-109">Se você sabe que essas informações serão inseridas para cursos, deve configurá-las antes de criar registros do curso.</span><span class="sxs-lookup"><span data-stu-id="73677-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="73677-110">**Grupos de salas de aula**</span><span class="sxs-lookup"><span data-stu-id="73677-110">**Classroom groups**</span></span>
-   <span data-ttu-id="73677-111">**Grupos de cursos**</span><span class="sxs-lookup"><span data-stu-id="73677-111">**Course groups**</span></span>
-   <span data-ttu-id="73677-112">**Locais do curso**</span><span class="sxs-lookup"><span data-stu-id="73677-112">**Course locations**</span></span>
-   <span data-ttu-id="73677-113">**Salas de aula**</span><span class="sxs-lookup"><span data-stu-id="73677-113">**Classrooms**</span></span>
-   <span data-ttu-id="73677-114">**Instrutores**</span><span class="sxs-lookup"><span data-stu-id="73677-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="73677-115">Tipos de cursos</span><span class="sxs-lookup"><span data-stu-id="73677-115">Course types</span></span>
<span data-ttu-id="73677-116">Você pode usar tipos de curso para categorizar os cursos de acordo com a estrutura ou o conteúdo do curso.</span><span class="sxs-lookup"><span data-stu-id="73677-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="73677-117">Você pode criar tipos de curso na página **Tipos de curso**.</span><span class="sxs-lookup"><span data-stu-id="73677-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="73677-118">Você deverá selecionar um tipo de curso ao criar um registro do curso.</span><span class="sxs-lookup"><span data-stu-id="73677-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="73677-119">Tipo de configuração de curso</span><span class="sxs-lookup"><span data-stu-id="73677-119">Course setup type</span></span>
<span data-ttu-id="73677-120">A tabela a seguir lista os três tipos de configuração para cursos.</span><span class="sxs-lookup"><span data-stu-id="73677-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="73677-121">Os tipos de configuração determinam a estrutura do curso.</span><span class="sxs-lookup"><span data-stu-id="73677-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="73677-122">Tipo de configuração</span><span class="sxs-lookup"><span data-stu-id="73677-122">Setup type</span></span></th>
<th><span data-ttu-id="73677-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="73677-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="73677-124"><strong>Padrão</strong></span><span class="sxs-lookup"><span data-stu-id="73677-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="73677-125">Selecione esse tipo para os cursos que não terão uma agenda diária.</span><span class="sxs-lookup"><span data-stu-id="73677-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="73677-126">Esse será o tipo padrão de configuração quando você criar um novo curso.</span><span class="sxs-lookup"><span data-stu-id="73677-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73677-127"><strong>Agenda</strong></span><span class="sxs-lookup"><span data-stu-id="73677-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="73677-128">Selecione esse tipo para planejar os detalhes de cada dia de um curso que dura vários dias.</span><span class="sxs-lookup"><span data-stu-id="73677-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="73677-129"><strong>Agenda + sessão</strong></span><span class="sxs-lookup"><span data-stu-id="73677-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="73677-130">Selecione esse tipo para os cursos mais complexos.</span><span class="sxs-lookup"><span data-stu-id="73677-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="73677-131">Por exemplo, você pode dividir a agenda do curso em controles e sessões.</span><span class="sxs-lookup"><span data-stu-id="73677-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="73677-132"><strong>Controle</strong> – Os controles são áreas de assunto específicas de um curso.</span><span class="sxs-lookup"><span data-stu-id="73677-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="73677-133"><strong>Sessões</strong> – As sessões são divididas em controles e ajudam a identificar processos ou técnicas específicas relevantes ao controle.</span><span class="sxs-lookup"><span data-stu-id="73677-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="73677-134">Tarefas do curso</span><span class="sxs-lookup"><span data-stu-id="73677-134">Course tasks</span></span>
<span data-ttu-id="73677-135">Para cada curso, você pode concluir as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="73677-135">For each course, you can complete the following tasks.</span></span>
- <span data-ttu-id="73677-136">Registrar participantes</span><span class="sxs-lookup"><span data-stu-id="73677-136">Register participants</span></span>
- <span data-ttu-id="73677-137">Especificar um prazo final para registro</span><span class="sxs-lookup"><span data-stu-id="73677-137">Specify a registration deadline</span></span>
- <span data-ttu-id="73677-138">Definir os números máximo e mínimo de participantes</span><span class="sxs-lookup"><span data-stu-id="73677-138">Define the minimum and maximum number of participants</span></span>
- <span data-ttu-id="73677-139">Atribuir um local do curso e uma sala de aula</span><span class="sxs-lookup"><span data-stu-id="73677-139">Assign a course location and classroom</span></span>
- <span data-ttu-id="73677-140">Recomendar hotéis aos participantes do curso</span><span class="sxs-lookup"><span data-stu-id="73677-140">Recommend hotels to course participants</span></span>
- <span data-ttu-id="73677-141">Criar uma descrição do curso, que pode ser anunciada no Autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="73677-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="73677-142">**Observação:** você pode excluir um curso somente se ninguém estiver registrado nele.</span><span class="sxs-lookup"><span data-stu-id="73677-142">**Note** You can delete a course only if no one has registered for it.</span></span> 

## <a name="course-statuses"></a><span data-ttu-id="73677-143">Status do curso</span><span class="sxs-lookup"><span data-stu-id="73677-143">Course statuses</span></span>
<span data-ttu-id="73677-144">A tabela a seguir lista os possíveis status do curso e as ações que poderão ser concluídas quando o curso tiver um status específico.</span><span class="sxs-lookup"><span data-stu-id="73677-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="73677-145">Status</span><span class="sxs-lookup"><span data-stu-id="73677-145">Status</span></span></th>
<th><span data-ttu-id="73677-146">Ações</span><span class="sxs-lookup"><span data-stu-id="73677-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="73677-147"><strong>Criado</strong></span><span class="sxs-lookup"><span data-stu-id="73677-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="73677-148">Inserir e modificar informações do curso.</span><span class="sxs-lookup"><span data-stu-id="73677-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="73677-149">Alterar o status do curso para <strong>Aberto</strong> de modo que os trabalhadores possam se registrar no curso.</span><span class="sxs-lookup"><span data-stu-id="73677-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73677-150"><strong>Abrir</strong></span><span class="sxs-lookup"><span data-stu-id="73677-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="73677-151">Registrar participantes no curso.</span><span class="sxs-lookup"><span data-stu-id="73677-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="73677-152">Remover participantes do curso.</span><span class="sxs-lookup"><span data-stu-id="73677-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="73677-153">Confirmar participantes no curso.</span><span class="sxs-lookup"><span data-stu-id="73677-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="73677-154">Alterar o status do curso para <strong>Fechado</strong> ou <strong>Cancelado</strong>.</span><span class="sxs-lookup"><span data-stu-id="73677-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="73677-155">Planejar questionários para participantes cujo status é <strong>Confirmado</strong>.</span><span class="sxs-lookup"><span data-stu-id="73677-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="73677-156"><strong>Fechado</strong></span><span class="sxs-lookup"><span data-stu-id="73677-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="73677-157">Você pode reabrir o curso.</span><span class="sxs-lookup"><span data-stu-id="73677-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73677-158"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="73677-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="73677-159">Você pode reabrir o curso.</span><span class="sxs-lookup"><span data-stu-id="73677-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="73677-160">Participantes do curso</span><span class="sxs-lookup"><span data-stu-id="73677-160">Course participants</span></span>
<span data-ttu-id="73677-161">Os participantes de curso são funcionários que estão participando de um curso de treinamento ou de um evento.</span><span class="sxs-lookup"><span data-stu-id="73677-161">Course participants are workers who participate in a training course or event.</span></span> <span data-ttu-id="73677-162">Você só pode registrar participantes em cursos em aberto.</span><span class="sxs-lookup"><span data-stu-id="73677-162">You can only register participants for open courses.</span></span> <span data-ttu-id="73677-163">Os números máximo e mínimo de participantes que você pode registrar para um curso é definido na Guia Rápida **Geral**, na página **Cursos**.</span><span class="sxs-lookup"><span data-stu-id="73677-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="73677-164">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="73677-164">Workflow</span></span>
--------

<span data-ttu-id="73677-165">Os funcionários que se registrarem em um curso na página **Autoatendimento para funcionários** podem ter seu registro roteado com o fluxo de trabalho para aprovação.</span><span class="sxs-lookup"><span data-stu-id="73677-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span> <span data-ttu-id="73677-166">Você pode atribuir um fluxo de trabalho a um curso na Guia Rápida **Geral** na página **Cursos**.</span><span class="sxs-lookup"><span data-stu-id="73677-166">You can assign a workflow to a course on the **General** FastTab on the **Courses** page.</span></span>





