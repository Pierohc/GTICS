    <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.10.24/css/jquery.dataTables.css">
    
     <table id="miTabla" class="display">
            <thead>
            <tr>
                <th>Número de Tracking</th>
                <th>Fecha de registro</th>
                <th>Estado</th>
                <th>Acciones</th>
            </tr>
            </thead>
            <tbody>
            <tr>
                <td>XXYYZZWW</td>
                <td>MM-DD-AA</td>
                <td>RECIBIDO</td>
                <td><a href="/paciente/tracking"><img width="24" height="24" src="https://img.icons8.com/material-outlined/24/visible--v1.png" alt="visible--v1"/></a></td>
            </tr>
            </tbody>
        </table>
    
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdn.datatables.net/1.10.24/js/jquery.dataTables.min.js"></script>
    <script>
        $(document).ready(function() {
            var table = $('#miTabla').DataTable({
                "pageLength":5,
                "lengthChange": false,
                "language": {
                    "emptyTable": "No hay registros disponibles",
                    "zeroRecords": "No se encontraron registros coincidentes",
                    "infoEmpty": "Mostrando 0 a 0 de 0 entradas",
                    "paginate": {
                        "first": "Primero",
                        "last": "Último",
                        "next": "Siguiente",
                        "previous": "Anterior"
                    },
                    "info": "Mostrando de _START_ a _END_ de _TOTAL_ entradas",
                },
    
            });
    
            $('#filtroEstado').on('change', function() {
                var estado = $(this).val();
                table.column(2).search(estado).draw();
    
            });
    
            $('#limpiarFiltros').on('click', function() {
                $('#filtroEstado').val('');
                table.search('').columns().search('').draw();
            });
        });
    
    
    </script>
