AUTOMAKE_OPTIONS = subdir-objects

bin_PROGRAMS = nix-tumor3d nix-tumor2d nix-compare3d nix-compare2d

nix_tumor3d_SOURCES = tumor.cpp AsciiIO.cpp Montecarlo.cpp Agent.cpp Angiogenesis.cpp CellProcesses.cpp DiffusionReactionEquation.cpp FiniteDifferences.cpp Interpolation.cpp Mathematix.cpp Molecule.cpp SparseMatrix.cpp Substrate.cpp EpsIO.cpp PovrayIO.cpp VesselGraph.cpp VesselUnit.cpp VesselNetwork.cpp VoronoiDiagramExtended.cpp
nix_tumor3d_LDADD = -lm  ../libnix/libnix.la
nix_tumor3d_CXXFLAGS = -DDIMENSIONS=3 -g

nix_tumor2d_SOURCES = tumor.cpp AsciiIO.cpp Montecarlo.cpp Agent.cpp Angiogenesis.cpp CellProcesses.cpp DiffusionReactionEquation.cpp FiniteDifferences.cpp Interpolation.cpp Mathematix.cpp Molecule.cpp SparseMatrix.cpp Substrate.cpp EpsIO.cpp PovrayIO.cpp VesselGraph.cpp VesselUnit.cpp VesselNetwork.cpp VoronoiDiagramExtended.cpp
nix_tumor2d_LDADD = -lm  ../libnix/libnix.la
nix_tumor2d_CXXFLAGS = -DDIMENSIONS=2

nix_compare3d_SOURCES = compare.cpp AsciiIO.cpp Montecarlo.cpp Agent.cpp Angiogenesis.cpp CellProcesses.cpp DiffusionReactionEquation.cpp FiniteDifferences.cpp Interpolation.cpp Mathematix.cpp Molecule.cpp SparseMatrix.cpp Substrate.cpp EpsIO.cpp PovrayIO.cpp VesselGraph.cpp VesselUnit.cpp VesselNetwork.cpp VoronoiDiagramExtended.cpp
nix_compare3d_LDADD = -lm ../libnix/libnix.la
nix_compare3d_CXXFLAGS = -DDIMENSIONS=3 -g

nix_compare2d_SOURCES = compare.cpp AsciiIO.cpp Montecarlo.cpp Agent.cpp Angiogenesis.cpp CellProcesses.cpp DiffusionReactionEquation.cpp FiniteDifferences.cpp Interpolation.cpp Mathematix.cpp Molecule.cpp SparseMatrix.cpp Substrate.cpp EpsIO.cpp PovrayIO.cpp VesselGraph.cpp VesselUnit.cpp VesselNetwork.cpp VoronoiDiagramExtended.cpp
nix_compare2d_LDADD = -lm ../libnix/libnix.la
nix_compare2d_CXXFLAGS = -DDIMENSIONS=2 -g
