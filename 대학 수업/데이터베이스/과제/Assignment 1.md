___

* suppliers (s$\#$, sname, city)
s$\#$은 공급사 번호, sname은 공급사명, city는 공급사가 위치한 도시를 가르킴.
공급사명은 유일함.
* parts (part$\#$, part_name, color, weight)
part$\#$는 부품 번호, color는 부품 색깔, weight는 부품 무게를 나타냄.
* projects (project$\#$, project_name, pcity)
pcity는 프로젝트가 수행되어지고 있는 도시를 가르킴.
* spj (s$\#$, part$\#$, project$\#$, quantity)
임의의 프로젝트에서 사용되는 부품과 해당 부품의 양, 해당 부품을 공급한 공급사 정보를 나타내는 Relation Schema이다. 

___

1) 부산에 위치한 공급사가 공급한 부품명(part_name)을 찾아라.

Sol)
$$\textrm{busan\_suppliers}\leftarrow \sigma_{\textrm{city = busan}}(\textrm{suppliers})$$
$$\textrm{busan\_spj} \leftarrow \textrm{busan\_suppliers} \bowtie \textrm{spj}$$
$$\Pi_{\textrm{part\_name}}(\textrm{busan\_spj} \bowtie \textrm{parts})$$
2)  제주에서 수행되고 있는 프로젝트들에 부품을 공급한 공급사들 중 제주에 위치한 공급사의 번호(s$\#$)을 찾아라.

Sol)
$$\textrm{jeju\_projects} \leftarrow \sigma_{\textrm{pcity = jeju}}(\textrm{projects})$$
$$\textrm{jeju\_project\_s\#}\leftarrow \Pi_{\textrm{s}\#}(\textrm{jeju\_projects}\bowtie\textrm{spj})$$
$$\Pi_{\textrm{s\#}}(\sigma_{\textrm{city = jeju}}(\textrm{jeju\_project\_s\#}\bowtie \textrm{suppliers}))$$
3) 부품의 무게 중 가장 무거운 무게를 찾아라.

Sol)
$$\mathcal{G}_{\max(\textrm{weight})}(\textrm{parts})$$
4) $A$ 공급사가 공급한 부품들의 총량을 찾아라.

Sol)
$$A\_\textrm{spj} \leftarrow \sigma_{\textrm{sname = }A}(\textrm{suppliers})\bowtie \textrm{spj}$$
$$\mathcal{G}_{\textrm{sum(quantity)}} (A\textrm{\_spj})$$
5) 공급사들 중 공급한 부품들의 총량(total quantity)이 $k$ 이상인 공급사명(sname)을 찾아라.

Sol)
$$\textrm{temp1} \leftarrow \textrm{suppliers}\bowtie \textrm{spj}$$
$$\textrm{temp2}\leftarrow _{\textrm{sname}}\mathcal{G}_{\textrm{sum(quantity) as s\_q}}(\textrm{temp1})$$
$$\Pi_{\textrm{sname}}(\sigma_{\textrm{s\_q}\geq k}(\textrm{temp2}))$$
6) 빨간색 부품을 적어도 하나 이상 공급한 공급사가 위치한 도시(city)를 찾아라.

Sol)
$$\textrm{temp1} \leftarrow \textrm{suppliers}\bowtie \textrm{spj}$$
$$\textrm{temp2} \leftarrow \textrm{temp1}\bowtie\textrm{parts}$$
$$\Pi_{\textrm{city}}(\sigma_{\textrm{color = red}}(\textrm{temp2}))$$
7) 셋 이상의 공급사에 의해 공급된 부품들을 사용한 프로젝트의 프로젝트 번호(project$\#$)와 프로젝트명(project_name)을 찾아라.

Sol)
$$\textrm{temp1} \leftarrow _{\textrm{project\#}}\mathcal{G}_{\textrm{count(s\#) as c\_s}}(\Pi_{\textrm{project\#,s\#}}(\textrm{spj}))$$
$$\textrm{temp2}\leftarrow \sigma_{c\_s \geq 3}(\textrm{temp1})$$
$$\Pi_{\textrm{project\#,project\_name}}(\textrm{temp2}\bowtie\textrm{projects})$$
8) 부품을 공급한 적이 없는 공급사명(sname)을 찾아라.

Sol)
$$\textrm{temp1}\leftarrow\Pi_{s\#}(\textrm{suppliers}) - \Pi_{s\#}(\textrm{spj})$$
$$\Pi_{\textrm{sname}}(\textrm{temp1}\bowtie\textrm{suppliers})$$
9) 모든 부품들의 부품번호(part$\#$), 부품명(part_name)을 찾아라. 단, 프로젝트에 공급된 적이 있는 부품은 해당 프로젝트 번호(project$\#$)와 공급량(quantity)을 함께 찾아라.(이때, 부품번호, 부품명은 두 번 이상 나타날 수도 있다.)

Sol)
$$\textrm{temp1}\leftarrow\textrm{spj} =\bowtie= \textrm{parts}$$
$$\Pi_{\textrm{part\#,part\_name,project\#,quantity}}(\textrm{temp1})$$
10) 공급사별로 부품을 공급한 프로젝트 수를 공급사명과 함께 찾아라.

Sol)
$$\textrm{temp1}\leftarrow(\textrm{suppliers}=\bowtie=\textrm{spj})$$
$$\textrm{temp2}\leftarrow\Pi_{\textrm{s\#,project\#,sname}}(\textrm{temp1})$$
$$\textrm{temp3} \leftarrow _{\textrm{s\#}}\mathcal{G}_{\textrm{count(project\#) as c\_p}}(\textrm{temp2})$$
$$\Pi_{\textrm{sname, c\_p}}(\textrm{temp3})$$