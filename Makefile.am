SUBDIRS = exporter utils etc templates sjconf doc data

dist_webengineapp_PYTHON = __init__.py urls.py webengine.fcgi
nodist_webengineapp_PYTHON =  settings.py webengine.wsgi
dist_doc_DATA = README.rst

edit = $(SED) \
	-e 's|@webenginedir[@]|$(webenginedir)|g' \
	-e 's|@webengineappdir[@]|$(webengineappdir)|g' \
	-e 's|@webenginesysconfdir[@]|$(webenginesysconfdir)|g'

settings.py: settings.py.in Makefile
	$(edit) $< > $@

webengine.wsgi: webengine.wsgi.in Makefile
	$(edit) $< > $@

dist_bin_SCRIPTS = \
	bin/we_acluser \
	bin/we_adduser \
	bin/we_chpasswd \
	bin/we_deluser \
	bin/we_listuser \
	bin/we_manageuser

CLEANFILES = settings.py webengine.wsgi
EXTRA_DIST = settings.py.in webengine.wsgi.in
