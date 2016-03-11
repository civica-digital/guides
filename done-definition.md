# Defintion of Done

> Done is better than perfect.

_Esta lista puede ir cambiando con el tiempo y conforme al equipo_

### ¿Cuándo está un feature / sprint / release listo para salir?

##### Feature

1. La funcionalidad cumple los criterios de aceptación definidos en la
   historia de usuario ([Pivotal Tracker](http://pivotaltracker.com/) || [Waffle.io](http://waffle.io) || [GitHub Issue](http://github.com)).
2. Cuenta con pruebas de integración pasando en verde, y no rompe con otras pruebas ya
   existentes previamente.
3. Los mensajes de los commits son descriptivos y en inglés. En caso de que sean demasiados
   commits que no ayudan a mantener un historial descriptivo, usa `git squash`.
4. El feature se encuentra en un branch `feature/name-of-feature`
   y los cambios con commits. Este branch se encuentra por encima de
`master`; en caso de que no, se puede hacer un `git rebase`.
5. El branch tiene un Pull-Request (PR) abierto a `master` y el botón de Merge está en verde.
6. El código del PR ha sido revisado por un colega del equipo, en
   caso de que no fue desarrollado en *pair programming*.
7. El PR se subió al ambiente de pruebas (staging server). La
   historia de usuario cambia a "Needs revision" (en GitHub issues) o "Deliver" (en Pivotal Tracker).
8. La funcionalidad fue aceptada por el Product Owner.
9. El PR es aceptado por el Delivery Owner o Dev Lead del equipo.
10. Realizar un deployment al ambiente de producción (production
    server).



