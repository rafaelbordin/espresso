# all the test scripts
tests= \
	nve_pe.tcl npt.tcl \
	madelung.tcl p3m.tcl el2d.tcl \
	el2d_nonneutral.tcl mmm1d.tcl dh.tcl \
	lj.tcl lj-cos.tcl tabulated.tcl gb.tcl \
	harm.tcl fene.tcl \
	kinetic.tcl thermostat.tcl \
	intpbc.tcl intppbc.tcl \
	layered.tcl nsquare.tcl \
	comforce.tcl comfixed.tcl \
	analysis.tcl \
	rotation.tcl \
	constraints.tcl \
	mass.tcl \
	lb.tcl

# add data files for the tests here
EXTRA_DIST = $(tests) \
	analysis_system.data.00.gz analysis_system.data.01.gz \
	analysis_system.data.02.gz analysis_system.data.03.gz \
	analysis_system.data.04.gz analysis_system.data.05.gz \
	analysis_system.data.06.gz analysis_system.data.07.gz \
	analysis_system.data.08.gz analysis_system.data.09.gz \
	analysis_system.data.10.gz analysis_system.data.chk \
	comforce_system.data comfixed_system.data \
	constraints_system.data \
	p3m_system.data el2d_system.data \
	mmm1d_system.data dh_system.data \
	lj_system.data lj-cos_system.data \
	gb_system.data \
	tabulated_system.data	lj1.tab lj2.tab lj3.tab \
	fene_system.data.gz harm_system.data.gz \
	intpbc_system.data.gz intppbc.tcl intppbc_system.data.gz \
	npt_lj_system.data \
	thermostat.data thermostat_rot.data \
	mass_system.data \
	lb_system.data \
	\
	pe_micelle.tcl pe_micelle_input.txt \
	uwerr_test.tcl uwerr_test.data

processors=1 2 3 4 6 8

# rules, don't fiddle around with that
TESTS_ENVIRONMENT=TESTCASES='$(tests)' PROCESSORS='$(processors)' ESPRESSO_SCRIPTS='$(srcdir)/scripts'
dist_check_SCRIPTS = test.sh
TESTS=test.sh

CLEANKEEPFILES=Makefile
clean-local:
	-for f in *; do keep=; \
		for cf in $(CLEANKEEPFILES); do if test "$$f" == "$$cf"; then keep=y; fi; done; \
		if test -z "$$keep"; then rm -f "$$f"; fi; done