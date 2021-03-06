###############################################################################
#
#    Particle Therapy Project Bergen (PTPB) - tools and models for research in
#    cancer therapy using particle beams.
#
#    Copyright (C) 2015 Particle Therapy Group Bergen
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU General Public License for more details.
#
#    You should have received a copy of the GNU General Public License
#    along with this program.  If not, see <http://www.gnu.org/licenses/>.
#
###############################################################################

# Top level make file to produce all calculations and plots.

OCTAVE = octave -q --path ~/bin/PTPB_mfiles

PATIENT_IDS = 12 33 35 36 37 39 41 42 43 44

.PHONY: all clean cleanall data plots \
  hypercubes clean-hypercubes cleanall-hypercubes \
  scan-plots clean-scan-plots cleanall-scan-plots \
  1d-samples clean-1d-samples cleanall-1d-samples \
  1d-scan-plots clean-1d-scan-plots cleanall-1d-scan-plots \
  per-patient-samples \
  clean-per-patient-samples \
  cleanall-per-patient-samples \
  per-patient-rbe-one-samples \
  clean-per-patient-rbe-one-samples \
  cleanall-per-patient-rbe-one-samples \
  per-patient-no-frac-samples \
  clean-per-patient-no-frac-samples \
  cleanall-per-patient-no-frac-samples \
  per-patient-no-alpha-spread-samples \
  clean-per-patient-no-alpha-spread-samples \
  cleanall-per-patient-no-alpha-spread-samples \
  per-patient-no-RBEmax-spread-samples \
  clean-per-patient-no-RBEmax-spread-samples \
  cleanall-per-patient-no-RBEmax-spread-samples \
  per-patient-no-alpha-RBEmax-spread-samples \
  clean-per-patient-no-alpha-RBEmax-spread-samples \
  cleanall-per-patient-no-alpha-RBEmax-spread-samples \
  per-patient-no-alpha-beta-RBEmax-spread-samples \
  clean-per-patient-no-alpha-beta-RBEmax-spread-samples \
  cleanall-per-patient-no-alpha-beta-RBEmax-spread-samples \
  per-patient-no-alpha-beta-RBE-spread-samples \
  clean-per-patient-no-alpha-beta-RBE-spread-samples \
  cleanall-per-patient-no-alpha-beta-RBE-spread-samples \
  samples clean-samples cleanall-samples \
  samples-no-alpha clean-samples-no-alpha cleanall-samples-no-alpha \
  samples-no-beta clean-samples-no-beta cleanall-samples-no-beta \
  samples-no-RBEmin clean-samples-no-RBEmin cleanall-samples-no-RBEmin \
  samples-no-RBEmax clean-samples-no-RBEmax cleanall-samples-no-RBEmax \
  samples-no-bin-spread clean-samples-no-bin-spread cleanall-samples-no-bin-spread \
  samples-no-spread clean-samples-no-spread cleanall-samples-no-spread


all: data
	@echo "Sampling is done. Now run with the 'plots' target to generate plots."

data: hypercubes \
  1d-samples \
  per-patient-samples \
  per-patient-rbe-one-samples \
  per-patient-no-frac-samples \
  per-patient-no-alpha-spread-samples \
  per-patient-no-RBEmax-spread-samples \
  per-patient-no-alpha-RBEmax-spread-samples \
  per-patient-no-alpha-beta-RBEmax-spread-samples \
  per-patient-no-alpha-beta-RBE-spread-samples \
  samples \
  samples-rbe-one \
  samples-no-frac \
  samples-no-alpha \
  samples-no-beta \
  samples-no-RBEmin \
  samples-no-RBEmax \
  samples-no-bin-spread \
  samples-no-spread

plots: scan-plots 1d-scan-plots

clean: clean-hypercubes \
  clean-scan-plots \
  clean-1d-samples \
  clean-1d-scan-plots \
  clean-per-patient-samples \
  clean-per-patient-rbe-one-samples \
  clean-per-patient-no-frac-samples \
  clean-per-patient-no-alpha-spread-samples \
  clean-per-patient-no-RBEmax-spread-samples \
  clean-per-patient-no-alpha-RBEmax-spread-samples \
  clean-per-patient-no-alpha-beta-RBEmax-spread-samples \
  clean-per-patient-no-alpha-beta-RBE-spread-samples \
  clean-samples \
  clean-samples-rbe-one \
  clean-samples-no-frac \
  clean-samples-no-alpha \
  clean-samples-no-beta \
  clean-samples-no-RBEmin \
  clean-samples-no-RBEmax \
  clean-samples-no-bin-spread \
  clean-samples-no-spread

cleanall: cleanall-hypercubes \
  cleanall-scan-plots \
  cleanall-1d-samples \
  cleanall-1d-scan-plots \
  cleanall-per-patient-samples \
  cleanall-per-patient-rbe-one-samples \
  cleanall-per-patient-no-frac-samples \
  cleanall-per-patient-no-alpha-spread-samples \
  cleanall-per-patient-no-RBEmax-spread-samples \
  cleanall-per-patient-no-alpha-RBEmax-spread-samples \
  cleanall-per-patient-no-alpha-beta-RBEmax-spread-samples \
  cleanall-per-patient-no-alpha-beta-RBE-spread-samples \
  cleanall-samples \
  cleanall-samples-rbe-one \
  cleanall-samples-no-frac \
  cleanall-samples-no-alpha \
  cleanall-samples-no-beta \
  cleanall-samples-no-RBEmin \
  cleanall-samples-no-RBEmax \
  cleanall-samples-no-bin-spread \
  cleanall-samples-no-spread


hypercubes:
	$(MAKE) -f hypercubes.makefile OCTAVE="$(OCTAVE)"

clean-hypercubes:
	$(MAKE) -f hypercubes.makefile clean

cleanall-hypercubes:
	$(MAKE) -f hypercubes.makefile cleanall


scan-plots:
	$(MAKE) -f scan_plots.makefile OCTAVE="$(OCTAVE)"

clean-scan-plots:
	$(MAKE) -f scan_plots.makefile clean

cleanall-scan-plots:
	$(MAKE) -f scan_plots.makefile cleanall


1d-samples:
	$(MAKE) -f alpha_scan_samples.makefile OCTAVE="$(OCTAVE)"
	$(MAKE) -f beta_scan_samples.makefile OCTAVE="$(OCTAVE)"
	$(MAKE) -f RBEmax_scan_samples.makefile OCTAVE="$(OCTAVE)"
	$(MAKE) -f RBEmin_scan_samples.makefile OCTAVE="$(OCTAVE)"

clean-1d-samples:
	$(MAKE) -f alpha_scan_samples.makefile clean
	$(MAKE) -f beta_scan_samples.makefile clean
	$(MAKE) -f RBEmax_scan_samples.makefile clean
	$(MAKE) -f RBEmin_scan_samples.makefile clean

cleanall-1d-samples:
	$(MAKE) -f alpha_scan_samples.makefile cleanall
	$(MAKE) -f beta_scan_samples.makefile cleanall
	$(MAKE) -f RBEmax_scan_samples.makefile cleanall
	$(MAKE) -f RBEmin_scan_samples.makefile cleanall


1d-scan-plots:
	$(MAKE) -f scan_1D_plots.makefile OCTAVE="$(OCTAVE)"

clean-1d-scan-plots:
	$(MAKE) -f scan_1D_plots.makefile clean

cleanall-1d-scan-plots:
	$(MAKE) -f scan_1D_plots.makefile cleanall


per-patient-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_samples.makefile PATIENT="$$N" cleanall ; \
	done


per-patient-rbe-one-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_rbe_one_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-rbe-one-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_rbe_one_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-rbe-one-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_rbe_one_samples.makefile PATIENT="$$N" cleanall ; \
	done


per-patient-no-frac-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_frac_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-no-frac-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_frac_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-no-frac-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_frac_samples.makefile PATIENT="$$N" cleanall ; \
	done


per-patient-no-alpha-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_spread_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-no-alpha-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_spread_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-no-alpha-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_spread_samples.makefile PATIENT="$$N" cleanall ; \
	done


per-patient-no-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_RBEmax_spread_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-no-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_RBEmax_spread_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-no-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_RBEmax_spread_samples.makefile PATIENT="$$N" cleanall ; \
	done


per-patient-no-alpha-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_RBEmax_spread_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-no-alpha-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_RBEmax_spread_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-no-alpha-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_RBEmax_spread_samples.makefile PATIENT="$$N" cleanall ; \
	done


per-patient-no-alpha-beta-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_beta_RBEmax_spread_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-no-alpha-beta-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_beta_RBEmax_spread_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-no-alpha-beta-RBEmax-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_beta_RBEmax_spread_samples.makefile PATIENT="$$N" cleanall ; \
	done


per-patient-no-alpha-beta-RBE-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_beta_RBE_spread_samples.makefile PATIENT="$$N" OCTAVE="$(OCTAVE)" ; \
	done

clean-per-patient-no-alpha-beta-RBE-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_beta_RBE_spread_samples.makefile PATIENT="$$N" clean ; \
	done

cleanall-per-patient-no-alpha-beta-RBE-spread-samples:
	for N in $(PATIENT_IDS) ; do \
		$(MAKE) -f patient_no_alpha_beta_RBE_spread_samples.makefile PATIENT="$$N" cleanall ; \
	done


samples:
	$(MAKE) -f samples.makefile OCTAVE="$(OCTAVE)"

clean-samples:
	$(MAKE) -f samples.makefile clean

cleanall-samples:
	$(MAKE) -f samples.makefile cleanall


samples-rbe-one:
	$(MAKE) -f samples_rbe_one.makefile OCTAVE="$(OCTAVE)"

clean-samples-rbe-one:
	$(MAKE) -f samples_rbe_one.makefile clean

cleanall-samples-rbe-one:
	$(MAKE) -f samples_rbe_one.makefile cleanall


samples-no-frac:
	$(MAKE) -f samples_no_frac.makefile OCTAVE="$(OCTAVE)"

clean-samples-no-frac:
	$(MAKE) -f samples_no_frac.makefile clean

cleanall-samples-no-frac:
	$(MAKE) -f samples_no_frac.makefile cleanall


samples-no-alpha:
	$(MAKE) -f samples_no_alpha.makefile OCTAVE="$(OCTAVE)"

clean-samples-no-alpha:
	$(MAKE) -f samples_no_alpha.makefile clean

cleanall-samples-no-alpha:
	$(MAKE) -f samples_no_alpha.makefile cleanall


samples-no-beta:
	$(MAKE) -f samples_no_beta.makefile OCTAVE="$(OCTAVE)"

clean-samples-no-beta:
	$(MAKE) -f samples_no_beta.makefile clean

cleanall-samples-no-beta:
	$(MAKE) -f samples_no_beta.makefile cleanall


samples-no-RBEmin:
	$(MAKE) -f samples_no_RBEmin.makefile OCTAVE="$(OCTAVE)"

clean-samples-no-RBEmin:
	$(MAKE) -f samples_no_RBEmin.makefile clean

cleanall-samples-no-RBEmin:
	$(MAKE) -f samples_no_RBEmin.makefile cleanall


samples-no-RBEmax:
	$(MAKE) -f samples_no_RBEmax.makefile OCTAVE="$(OCTAVE)"

clean-samples-no-RBEmax:
	$(MAKE) -f samples_no_RBEmax.makefile clean

cleanall-samples-no-RBEmax:
	$(MAKE) -f samples_no_RBEmax.makefile cleanall


samples-no-bin-spread:
	$(MAKE) -f samples_no_bin_spread.makefile OCTAVE="$(OCTAVE)"

clean-samples-no-bin-spread:
	$(MAKE) -f samples_no_bin_spread.makefile clean

cleanall-samples-no-bin-spread:
	$(MAKE) -f samples_no_bin_spread.makefile cleanall


samples-no-spread:
	$(MAKE) -f samples_no_spread.makefile OCTAVE="$(OCTAVE)"

clean-samples-no-spread:
	$(MAKE) -f samples_no_spread.makefile clean

cleanall-samples-no-spread:
	$(MAKE) -f samples_no_spread.makefile cleanall
