# Projekt_Engeto
Závěrečný úkol

import pytest

@pytest.mark.playwright
def test_courses_button_clickable(page):
    page.goto("https://engeto.cz")

    courses_button = page.locator("text=Kurzy")
    assert courses_button.is_visible()
    courses_button.click()

    assert "kurzy" in page.url

@pytest.mark.playwright
def test_homepage_title_contains_engeto(page):
    page.goto("https://engeto.cz")

    assert "Engeto" in page.title()

@pytest.mark.playwright
def test_contact_page_contains_text(page):
    page.goto("https://engeto.cz")

    contact_link = page.locator("text=Kontakt")
    contact_link.click()

    assert page.locator("text=Kontaktujte nás").is_visible()
