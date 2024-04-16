## 1. **th:text**: `<p>`, `<span>`, `<h1>`, `<div>`, etc.

   ```html
   <p th:text="${texto}"></p>
   <span th:text="${texto}"></span>
   <h1 th:text="${texto}"></h1>
   ```

   ![image](https://github.com/Pierohc/GTICS/assets/133154904/5a47de45-c385-499e-a492-16a88878f792)

   ![image](https://github.com/Pierohc/GTICS/assets/133154904/b6685bb6-75bb-4cd9-a341-30778c58ef6c)


<br>
<br>
<br>
 <br>
 <br>



   

## 2. **th:each**: `<table>`, `<ul>`, `<ol>`, etc.

   ```html
   <table>
       <tr th:each="item : ${items}">
           <td th:text="${item}"></td>
       </tr>
   </table>
   ```

   ![image](https://github.com/Pierohc/GTICS/assets/133154904/68f3423b-220f-4320-83b8-102d270b5d0e)

   ![image](https://github.com/Pierohc/GTICS/assets/133154904/9ae14b0a-537d-40f1-bb87-55a140451616)

   ![image](https://github.com/Pierohc/GTICS/assets/133154904/9ac8029e-32a8-453a-ac7e-77a026c4161b)

  ## Para un Combobox:
  
  ![image](https://github.com/Pierohc/GTICS/assets/133154904/08e8f122-ad72-4254-bc43-bd6e3db78308)



  <br>
<br>
<br>
 <br>
 <br>


## 3. **th:if / th:unless**: `<div>`, `<span>`, `<p>`, etc.

   ### Variacion para agregar un style:

         <div class="item-title roboto-regular"
           th:text="${medicamento.nombre}"
           th:style="${medicamento.nombre.length() > 20 ? 'font-small' : ''}">
           Medicamento
      </div>


---------------------------------------

   ```html
   <div th:if="${condicion}">Contenido</div>
   <span th:unless="${condicion}">Contenido alternativo</span>
   ```

![image](https://github.com/Pierohc/GTICS/assets/133154904/7a67330f-3bbd-401b-b034-a0f13b715c60)

![image](https://github.com/Pierohc/GTICS/assets/133154904/222b0b3c-5a77-4bd5-90b2-b67aa143ab8b)

![image](https://github.com/Pierohc/GTICS/assets/133154904/bf11a74c-60a4-44f5-9146-a2a982f0d585)

![image](https://github.com/Pierohc/GTICS/assets/133154904/4894dc26-2c01-41d9-90be-01abbb501d9f)

![image](https://github.com/Pierohc/GTICS/assets/133154904/741e43cc-76ae-4467-b262-fb2445c95e61)

![image](https://github.com/Pierohc/GTICS/assets/133154904/7ed31f30-ca7b-422c-9ad3-1b3705dae69a)

 <br>
<br>
<br>
 <br>
 <br>

## 4. **th:href / th:src**: `<a>`, `<link>`, `<script>`, `<img>`, etc.

   ```html
   <a th:href="@{/ruta/dinamica}">Enlace</a>
   <img th:src="@{/ruta/dinamica/imagen.jpg}" alt="Imagen">
   ```

   ![image](https://github.com/Pierohc/GTICS/assets/133154904/ab580ace-f464-468b-9835-2581348133f2)


7. **th:switch / th:case**: `<div>`, `<span>`, etc.

   ```html
   <div th:switch="${variable}">
       <span th:case="1">Caso 1</span>
       <span th:case="2">Caso 2</span>
       <span th:case="*">Caso predeterminado</span>
   </div>
   ```

8. **th:class**: `<div>`, `<span>`, `<p>`, etc.

   ```html
   <div th:class="${condicion} ? 'clase-activa' : 'clase-inactiva'">Contenido</div>
   ```

9. **th:id**: Cualquier elemento HTML que necesite un ID.

   ```html
   <div th:id="${identificador}">Contenido</div>
   ```

10. **th:style**: Cualquier elemento HTML que necesite estilos CSS.

   ```html
   <div th:style="'background-color: ' + ${color} + ';'">Contenido</div>
   ```

11. **th:attr**: Cualquier elemento HTML que necesite atributos adicionales.

   ```html
   <input type="text" th:attr="data-id=${id}" />
   ```

11. **th:disabled**: `<input>`, `<button>`, etc.

    ```html
    <input type="submit" th:disabled="${condicion}" value="Enviar" />
    ```

12. **th:selected**: `<option>` dentro de un `<select>`.

    ```html
    <select>
        <option th:selected="${condicion}" value="1">Opción 1</option>
        <option th:selected="${!condicion}" value="2">Opción 2</option>
    </select>
    ```

13. **th:checked**: `<input type="checkbox">`, `<input type="radio">`, etc.

    ```html
    <input type="checkbox" th:checked="${condicion}" />
    ```

14. **th:value**: `<input>`, `<textarea>`, etc.

    ```html
    <input type="text" th:value="${valor}" />
    <textarea th:value="${texto}"></textarea>
    ```

15. **th:placeholder**: `<input>`, `<textarea>`, etc.

    ```html
    <input type="text" th:placeholder="Ingrese su nombre" />
    ```

16. **th:alt**: `<img>`, etc.

    ```html
    <img th:alt="${texto}" th:src="${url}" />
    ```

17. **th:title**: Cualquier elemento HTML que necesite un título.

    ```html
    <div th:title="${titulo}">Contenido</div>
    ```

18. **th:fragment**: Define fragmentos que pueden ser incluidos en otras partes de la plantilla.

    ```html
    <div th:fragment="miFragmento">
        Contenido del fragmento
    </div>
    ```

19. **th:remove**: Elimina elementos HTML basados en una condición.

    ```html
    <div th:remove="${condicion}"></div>
    ```

20. **th:object**: Define el objeto al que se refiere el contexto de la iteración.

    ```html
    <div th:each="item : ${items}" th:object="${item}">
        <span th:text="${item.nombre}"></span>
    </div>
    ```

21. **th:inline**: Permite la inclusión de scripts y fragmentos HTML inline.

    ```html
    <script th:inline="javascript">
        var data = [[${datos}]];
    </script>
    ```

