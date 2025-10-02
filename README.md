# Gestor-de-Tareas-
Evaluacion 2 Django
Abrir shell
python manage.py shell

from tareas.models import Tarea from django.utils import timezone

Crear
Tarea.objects.create(titulo='Tarea 1', descripcion='Realizar tarea 1', prioridad=1, vigente=True)

Listar
Tarea.objects.all()

Filtrar por prioridad alta (1 a 4)
Tarea.objects.filter(prioridad__lte=4).order_by('prioridad')

Obtener una tarea, editar y guardar
t = Tarea.objects.get(pk=1) t.vigente = False t.save()

Borrar
Tarea.objects.filter(vigente=False).delete()

Conteo
Tarea.objects.count()

Tareas con fecha límite pasada
Tarea.objects.filter(fecha_limite__lt=timezone.now().date())
