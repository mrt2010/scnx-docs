---
description: Die Verwendung von Verknüpften Rollen kann kompliziert sein und es treten leicht Probleme auf.
sidebar_position: 5
---

# Fehlerbehebung

Die Verwendung von Verknüpften Rollen kann kompliziert sein, und es treten leicht Probleme auf. In diesem Dokument schauen wir uns häufige Probleme und Lösungen dazu an.

## Übersicht {#content}

Bitte wähle das Problem aus, das bei dir auftritt.

Probleme während der Einrichtung:

* [Ich kann die Link-Anforderung nicht zu einer Discord-Rolle hinzufügen](#link-requirement).

Probleme bei der Verwendung von Verknüpften Rollen:

* [Die Verknüpfte Rolle wird im Chat nicht angezeigt](#display-missing).
* [Nutzer erhalten die Verknüpfte Rolle nicht](#role-not-given).
* ["Invalid OAuth2 redirect_url" beim Abholen von Verknüpften Rollen](#oauth2-redirect-url).
* ["Es wurden dir noch keine Rollen zugewiesen" beim Abholen von Verknüpften Rollen](#roles-missing).
* ["Es scheint, als wäre die Konfiguration des Servers falsch" beim Abholenn von Verknüpften Rollen](#generic-api-error).
* ["Der SCNX-Plan dieses Servers ist abgelaufen" beim Abholen von Verknüpften Rollen](#plan-expired).

Wenn dein Problem hier nicht aufgeführt ist, [klicke hier](#other).

## Probleme bei der Einrichtung & Konfiguration {#setup}

### Link-Anforderung kann nicht gespeichert werden {#link-requirement}

Beim [Einrichten einer Verknüpften Rolle auf Discord](/docs/linked-roles/role-management#linked-role-on-discord) kann der Fehler „Ungültige Rolle“ auftreten, wenn du die Link-Anforderung zu einer Discord-Rolle hinzufügst.

**Lösung**: Du kannst keine Link-Anforderungen zu Rollen hinzufügen, die bereits Mitglieder haben. Entferne die Rolle von allen Mitgliedern oder erstelle eine neue Rolle.

## Probleme bei der Verwendung von Verknüpften Rollen {#usage}

### Die Rolle wird nicht im Chat angezeigt {#display-missing}

Bei der Verwendung von Verknüpften Rollen kann es vorkommen, dass die Rolle nicht neben dem Benutzernamen im Chat angezeigt wird.

**Lösung**: Damit die Verknüpfte Rolle neben dem Benutzernamen angezeigt wird, musst du in jedem Kanal eine Berechtigungsüberschreibung mit der Berechtigung „Kanal ansehen“ für die Verknüpfte Rolle erstellen.
[Mehr dazu findest du in unserem Leitfaden](/docs/linked-roles/role-management#display-in-chat).

### "Es scheint, als wäre die Konfiguration des Servers falsch" beim Abholen von Verknüpften Rollen {#generic-api-error}

Wenn ein Schritt während der Einrichtung übersprungen wurde oder ein falscher Wert eingegeben wurde, können Verknüpfte Rollen nicht korrekt synchronisiert werden.

**Lösung**:

Um dieses Problem zu beheben, musst du einige Schritte der [Einrichtung](/docs/linked-roles/) erneut durchführen. Folge diesen Schritten:

1. Setze die Authentifizierungsdetails auf deiner [Verknüpfte Rollen-Konfigurationsseite](https://scnx.app/de/glink?page=linked-roles/configuration) zurück. Klicke dazu auf „Authentifizierungsdetails zurücksetzen“ oder folge [dieser Anleitung](/docs/linked-roles/settings/#reset-auth-details).
2. Danach wirst du in deinem Dashboard aufgefordert, alle Einrichtungsschritte erneut durchzuführen.
3. Folge unserem [Einrichtungsleitfaden](/docs/linked-roles#step-2) ab Schritt 2. Achte genau auf alle Anweisungen, da Fehler zu diesem Problem führen können.
4. Sobald du fertig bist, versuche erneut, die [Rolle einzufordern](/docs/linked-roles/claim-roles/).

### "Es wurden dir noch keine Rollen zugewiesen" beim Abholen von Verknüpften Rollen {#roles-missing}

Standardmäßig müssen Rollen im Dashboard manuell zugewiesen werden. Wenn keine Rollen zugewiesen wurden, erscheint dieser Fehler.

**Lösung**: [Weise dem entsprechenden Nutzer eine Rolle zu](/docs/linked-roles/user-management/#add-role) oder mache
die [Rolle öffentlich](/docs/linked-roles/role-management/#public-roles), sodass sie von allen beansprucht werden kann. Wenn du denkst, dass eine Rolle zugewiesen wurde, vergewissere dich, dass der Nutzer mit dem richtigen Account eingeloggt ist.

### "Invalid OAuth2 redirect_url" beim Abholen von Verknüpften Rollen {#oauth2-redirect-url}

Beim Einrichten von Verknüpften Rollen muss die Weiterleitungs-URL im Discord Developer Portal gespeichert werden, sonst erscheint dieser Fehler.

**Lösung**:

1. Öffne deine [Verknüpfte Rollen-Konfigurationsseite](https://scnx.app/de/glink?page=linked-roles/configuration) und kopiere die „Redirect URL“ aus der Karte „Autorisierungsdetails“. Sie sollte in etwa so aussehen:
   `https://linked-roles.scnx.app/api/b4e5e89a-1c92-11f0-b688-03c2706e348f/callback` (der mittlere Teil kann je nach Server variieren).
2. Öffne das [Discord Developer Portal](https://discord.com/developers/applications) und wähle deinen Bot aus.
3. Gehe zum Reiter „OAuth2“ deines Bots und klicke auf „Add Another“ im Abschnitt „Redirects“.
4. Füge die kopierte Redirect-URL ein und speichere die Änderungen.
5. Versuche erneut, die [Rolle einzufordern](/docs/linked-roles/claim-roles).

![Dieser Screenshot zeigt, wo die kopierte Redirect-URL eingefügt werden muss](@site/docs/assets/linked-roles/setup/enter-redirect-url.webp)

### Nutzer erhalten die Verknüpfte Rolle nicht {#role-not-given}

Bei der Verwendung von Verknüpften Rollen erhalten Nutzer die Rolle nicht automatisch.

**Lösung**: Nutzer müssen die [Verknüpfte Rolle manuell abholen](/docs/linked-roles/claim-roles/). Du kannst ihnen folgenden Link senden: [`https://scootk.it/claim-linked-roles`](https://scootk.it/claim-linked-roles).

### "Der SCNX-Plan dieses Servers ist abgelaufen" beim Abholen von Verknüpften Rollen {#plan-expired}

Für die Nutzung von Verknüpften Rollen ist ein Plan erforderlich, der diese Funktion beinhaltet.

**Lösung**: Upgrade auf einen kostenpflichtigen Plan, der Verknüpfte Rollen unterstützt. Erfahre mehr
über [Pläne und deren Funktionen in unserer Dokumentation](/docs/scnx/guilds/plans/).

## Andere Probleme {#other}

Oh nein, das ist merkwürdig – wir helfen dir gerne weiter, entweder in unserem [Discord](https://scootk.it/dc-de) oder
auf [scnx.app/help](https://scnx.app/help).