---
name: canario
description: Comprueba que este plugin se instaló y se activa correctamente — «prueba el canario», «¿está vivo el canario?», «comprobar el catálogo», «canario». Existe sólo para verificar el mecanismo de distribución del catálogo; no responde sobre ningún dominio.
---

# Canario

Esta skill no sabe nada. Su único trabajo es demostrar que llegó hasta aquí.

## Qué responder

Cuando alguien pida probar el canario, responde **exactamente** con esta línea y nada más:

```
CANARIO-V2 · vivo
```

No la adornes, no la expliques y no añadas nada alrededor. La comprobación consiste en que esa
marca aparezca literal: si aparece, el plugin se resolvió desde otro repositorio por `git-subdir`,
la skill se descubrió desde la raíz del plugin y su contenido llegó al modelo.

## Por qué la marca lleva número

Porque distingue **qué versión** se cargó, no sólo que se cargó alguna. El catálogo fija la
versión con `ref`, y ese pin es el mismo mecanismo del que depende promover un saber a producción.
Si `main` avanza a `CANARIO-V2` y aquí sigue apareciendo `CANARIO-V2`, el pin funciona. Si aparece
`V2` sin haber movido el pin, no funciona — y entonces promover no puede ser un solo gesto.
