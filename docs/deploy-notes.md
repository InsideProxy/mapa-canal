# Deploy Notes — proxy-mapa

## URLs
- **Netlify (live):** https://proxy-mapa.netlify.app
- **Netlify Site ID:** ca9ae4cc-dc17-4f33-8b23-d10e55e61f37
- **GitHub repo:** https://github.com/SharedLaberinto/proxy-mapa

## Estado actual del deploy

### Problema: Cuenta GitHub flaggeada
La cuenta **SharedLaberinto** esta flaggeada por GitHub, lo que impide:
- GitHub Actions (no se pueden habilitar)
- GitHub Pages (no funciona)
- Autorizar apps de terceros (Netlify no puede conectarse al repo para auto-deploy)

### Causa probable
La cuenta no tenia 2FA activado. Ya se activo, pero el flag persiste hasta que GitHub soporte lo revise.

### Contacto soporte GitHub
- URL: https://support.github.com/contact/account
- Alternativa: https://github.com/contact -> "Flagged Account"
- Tiempo de respuesta: 1-3 dias laborables
- Explicar que la cuenta SharedLaberinto esta flaggeada y no permite Actions ni autorizar apps de terceros

## Deploy manual (mientras tanto)

Desde la raiz del proyecto:

```bash
netlify deploy --prod --dir=. --site ca9ae4cc-dc17-4f33-8b23-d10e55e61f37
```

## Cuando se desflaggee la cuenta

1. Ir a https://app.netlify.com -> proxy-mapa -> Site settings -> Build & deploy -> Link repository
2. Conectar el repo SharedLaberinto/proxy-mapa
3. Branch: main
4. A partir de ahi, cada push a main auto-despliega

## Alternativa: Mover repo a IBabitsch
Si el flag tarda mucho:
- Crear repo en la cuenta IBabitsch (sin restricciones)
- Anadir SharedLaberinto como collaborator
- Conectar Netlify via IBabitsch -> auto-deploy funciona
- Companero edita directamente en GitHub web (boton Edit)
